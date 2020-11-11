Drill down to specific box using URL parameter
==============================================

In this quick tip I will describe how to navigate to specific box in your org chart using URL parameter. 
It may be useful if you want to place link to specific box to other page. 
For example, you can use it to open org chart starting from manager of specific department. 
Some of our customers use this approach to add link to employees search results. 
Thus, you can navigate to person in org chart directly from search results.


This works in Org Chart for SharePoint 2010, SharePoint 2013/2016 and in Org Chart for Office 365.

In my case Org Chart web part is located here:



https://plumsail.sharepoint.com/orgchart.aspx


I want to be able to navigate to specific box using URL like this:



https://plumsail.sharepoint.com/orgchart.aspx?**boxID=account@plumsail.com**



Depending on your configuration Org Chart uses some property as ID of the box. 
In my case it is an email (account name of user in Office 365). 
If you use SharePoint list as a data source it can be other field value, for example list item ID. 
If you use SharePoint On-Premises it can be domain account name like **domain\accountname**. 
Thus, boxID is just identificator of employee.


Open the configuration wizard of Org Chart, navigate to ‘Custom JavaScript’ step and paste this code into code editor:

.. code:: JavaScript

   var boxId = GetUrlKeyValue("boxID");
 
   //if there is boxID in URL
   if(boxId) {
 
    //Skip initiall node rendering
    renderer.config.renderInitialNode = false;
 
    //Wait for web part loading
    renderer.onInitialLoadingFinished(function(){
      //Drill down to box from URL parameter
      renderer.drillDown(boxId); 
    });
 
   }


.. image:: /../_static/img/how-tos/show-specific-user-on-load/drill-down-to-specific-box-using-url-parameter/DrillDownToUserWizard.png
    :alt: Drill down to user


Finish the wizard. That is it! Now you can navigate to specific box in your organizational structure using URL parameter.

If you are interesting in how it works, read explanation below.


When your web part is loaded, custom JavaScript code is executed. This code checks that there is boxID parameter in URL. 
If it is there, it disables rendering of default root node, waits for web part loading and performs drill down to employee with ID specified in the URL parameter.
