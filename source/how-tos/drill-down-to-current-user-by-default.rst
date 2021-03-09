How to drill down to current user by default for Org Chart in SharePoint and Microsoft Teams
============================================================================================

In this tip I want to cover such case as drilling down to current user by default on Org Chart load. 
We see such questions frequently and decided to cover it in our blog.

Org Chart supports two data sources: User Profiles and SharePoint list. 
I will show how to implement drill down to current user for both.

.. contents::
   :local:
   :depth: 1

.. _user-profiles:

Drill down to current user on Org Chart load for User Profiles
--------------------------------------------------------------

If you have SharePoint Online (Office 365) or SharePoint 2019, 2016, 2013 it is quite simple to implement such drill down for User Profiles data source using `JavaScript framework <../javascript-framework/introduction.html>`_. 
Just open the configuration wizard and paste the code below to JavaScript editor on **Custom JavaScript** step.

.. code-block:: javascript

  renderer.config.renderInitialNode = false;
  
  renderer.onInitialLoadingFinished(function () {

    renderer.dataProvider.getCurrentUserAccountName(function (accountName) {
      renderer.drillDown(accountName);
    });

  });

If you have SharePoint 2010 use the code below. It is more complex than the code above.

.. code-block:: javascript

  var currentUserLogin;
  var isInitialLoad = true;

  renderer.prerenderAction = function (completed) {
    try {
      var context = SP.ClientContext.get_current()
      var web = context.get_web()
      var user = web.get_currentUser()
      context.load(user);

      context.executeQueryAsync(function () {
        currentUserLogin = user.get_loginName();
        completed();
      }, function (sender, args) {
        console.log("Unable to get current user login");
        console.log(args);
        completed();
      });

    } catch (e) {
      completed();
    }
  }

  renderer.onLoadingFinished(function () {
    if (isInitialLoad) {
      isInitialLoad = false;
      renderer.drillDown(currentUserLogin);
    }
  });

See the screenshot below for example:

.. image:: /../_static/img/how-tos/show-specific-user-on-load/drill-down-to-current-user-by-default/UserProfilesDrillDownScript-1.png
    :alt: Drill down to user

.. _sharepoint-list:

Drill down to current user on Org Chart load for SharePoint list
----------------------------------------------------------------

It is more difficult to implement such behavior for SharePoint list. 
First of all we have to ensure that we have field with account name of user in our SharePoint list. 
In my case I created list field called "AccountName". 
Then I used `JSOM <https://msdn.microsoft.com/en-us/library/office/hh185007(v=office.14).aspx>`_ to find list item by account name of current user. 
I used CAML query to do this. 
Once I have list item for current user I can read ID of for this item and drill down to it using `JavaScript framework <../javascript-framework/introduction.html>`_. 
Actually you can just copy and paste the code below to JavaScript editor on **Custom JavaScript** step of the configuration wizard. 
The only thing you may need to replace is internal name of field where account name of user is stored in SharePoint list. 
Just replace :code:`AccountName` with your field internal name:

.. code-block:: javascript

  var loginFieldInternalName = "AccountName";

And it is complete script to copy paste:

.. code-block:: javascript

  function getCurrentUserOrgChartId(completed, error) {

    var camlQueryTemplate = "<View><Query><Where><Eq><FieldRef Name='{{loginFieldInternalName}}'/><Value Type='Text'>{{currentUserLogin}}</Value></Eq></Where></Query></View>";
    var listId = renderer.config.ListDataSourceSettings.ListId;
    var orgChartIdFieldName = renderer.config.idFieldMapping.InternalFieldName;

    var context = SP.ClientContext.get_current();

    renderer.dataProvider.getCurrentUserAccountName(function (currentUserLogin) {
      console.log("currentUserLogin:", currentUserLogin);
      currentUserLogin = currentUserLogin.replace(/.*\|/, "");

      var list = context.get_web().get_lists().getById(listId);
      var camlQuery = new SP.CamlQuery();
      var queryText = camlQueryTemplate
        .replace("{{loginFieldInternalName}}", loginFieldInternalName)
        .replace("{{currentUserLogin}}", currentUserLogin);

      console.log("queryText: ", queryText);

      camlQuery.set_viewXml(queryText);
      var foundItems = list.getItems(camlQuery);

      context.load(foundItems);

      context.executeQueryAsync(function () {
        f = foundItems;
        var en = foundItems.getEnumerator();
        if (en.moveNext()) {
          var fieldValuesForCurrentUser = en.get_current().get_fieldValues();
          var currentUserOrgChartId = fieldValuesForCurrentUser[orgChartIdFieldName];
          completed(currentUserOrgChartId);
        } else {
          console.log("List item for current user not found.");
        }
      }, function (sender, args) {
        error(args);
      });
    });

  }

  var currentUserId = "";
  var loginFieldInternalName = "AccountName";

  renderer.prerenderAction = function (completed) {
    getCurrentUserOrgChartId(function (userId) {
      currentUserId = userId;
      completed();
    }, function (errorArgs) {
      console.log(errorArgs);
      completed();
    });
  }

  renderer.onInitialLoadingFinished(
    function () {
      if (currentUserId) {
        renderer.drillDown(currentUserId);
      }
    }
  );
