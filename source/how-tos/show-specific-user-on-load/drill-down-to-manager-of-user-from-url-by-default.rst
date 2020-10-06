Drill down to manager of user from URL by default
=================================================

In this quick tip, I will describe how to drill down to a manager of a user based on a URL parameter on Org Chart load. 
It may be useful if you want Org Chart to behave as standard SharePoint Org Chart. 
You can place Org Chart on a user profile page. 
It will take “accountname” URL parameter and drill down to a manager of this user on Org Chart load. 
If there no URL parameter it will drill down to a manager of a current user. 
If there is no manager, it will drill down to this user.


This works in Org Chart for SharePoint 2019 / 2016 / 2013 and in Org Chart for Office 365.

In my case, Org Chart web part is located here:

.. code::

  htts://plumsail.sharepoint.com/orgchart.aspx


I want to be able to drill down to a manager of a user using URL like this:

.. code::

  htts://plumsail.sharepoint.com/orgchart.aspx?accountname=account@plumsail.com


Depending on your configuration Org Chart uses some property as ID of the box. 
In my case it is an email (account name of a user in Office 365). 
If you use SharePoint list as a data source it can be other field value. 
For example, list item ID. If you use SharePoint On-Premises it can be domain account name like **domain\accountname**. 
Thus, “accountname” is just identificator of employee.

Open the configuration wizard of Org Chart, navigate to ‘Custom JavaScript’ step and paste this code into code editor:

.. code::

   var accountNameFromUrl = GetUrlKeyValue("accountname");
 
   function drillDownToManagerOfUser(accountName){
 
       renderer.dataProvider.getBoxGroupItemDataById(accountName, 
           function (dataItem) {
 
           if (dataItem.ParentId) {
              console.log("Drilling down to manager: " + dataItem.ParentId);
              renderer.drillDown(dataItem.ParentId);
          } else {
              console.log("Drilling down to user: " + accountName);
              renderer.drillDown(accountName);
          }
 
      });
   }
 
   //Don't wait for loading of initial root employee
   renderer.config.renderInitialNode = false;
 
   //Wait for web part loading
   renderer.onInitialLoadingFinished(function () {    
 
     //if there is accountNameFromUrl in URL
     if (!accountNameFromUrl) {
        
         //Drill down to current user's manager if exists
         renderer.dataProvider.getCurrentUserAccountName(function (accountName) {            
             drillDownToManagerOfUser(accountName)
         })
 
     } else {
 
         //Drill down to a manager of a user from URL if exists
         drillDownToManagerOfUser(accountNameFromUrl)
 
     }
 
   });


.. image:: /../../_static/img/how-tos/show-specific-user-on-load/drill-down-to-manager-of-user-from-url-by-default/DrillDownToManagerofUserWizard.png
    :alt: Drill down to manager


Finish the wizard. That is it! Now you can navigate to manager of a user according to a URL parameter.


How it works
------------

When your web part is loaded, custom JavaScript code is executed. This code disables initial rendering of web part to make drill down instead of waiting for web part loading:

.. code::

   renderer.config.renderInitialNode = false;


Then it checks if there is URL parameter accountname. If the URL parameter is not specified, it gets current user account name and tries to drill down to a manager of a current user. If there is no manager, it drills down to a current user:

.. code::

   //Drill down to current user's manager if exists
   renderer.dataProvider.getCurrentUserAccountName(function (accountName) {            
       drillDownToManagerOfUser(accountName)
   })

If the URL parameter is specified it tries to drill down to a manager of account name from the URL parameter:

.. code::

   //Drill down to a manager of a user from URL if exists
   drillDownToManagerOfUser(accountNameFromUrl)


Drill down logic is implemented in “drillDownToManagerOfUser” JavaScript function:


.. code::

   function drillDownToManagerOfUser(accountName){
     
    renderer.dataProvider.getBoxGroupItemDataById(accountName, 
        function (dataItem) {
 
        if (dataItem.ParentId) {
            console.log("Drilling down to manager: " + dataItem.ParentId);
            renderer.drillDown(dataItem.ParentId);
        } else {
            console.log("Drilling down to user: " + accountName);
            renderer.drillDown(accountName);
        }
 
      });
   }