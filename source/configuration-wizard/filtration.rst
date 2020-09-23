Filtration
===========

You can use filters to exclude people from the chart or show just specific departments or employees. 
You may filter by department, name, or by any other field.

For example, using this filter you can show employees from Marketing department only:

.. code:: javascript

1. return itemData["Department"].contains("Marketing");


And with this filter, you can exclude all employees whose name contains Smith:

.. code::

1. return !itemData["PreferredName"].contains("Smith");


You may check this article (link) for more information.

.. image:: /../_static/img/advanced-web-part-configuration/filtration/OrgChart-Configuration-Wizard-3.png
    :alt: Filtration

.. rubric:: Starting employee

By default you can start the hierarchy from a specific employee. 
Just start typing the employee name and OrgChart will suggest some matching names.

You can leave starting employee field empty. In this case the following logic will be used:

- If User profiles were chosen as a data source, starting employee will be located based on current user relations. The current person will be found, then the Org Chart will traverse up by manager relation until a person without a manager is found. The person without manager will be displayed as a starting employee.
- If SharePoint list were chosen as a data source, the first employee found without manager item will be taken as a starting employee.

.. rubric:: Org Chart filtration

You can include or exclude items from the Org Chart using the filtration rule. For example this rule will only include employees from the Marketing department:

.. code::

    function(itemData){

       //You can get field values like this: itemData["Department"]
       return itemData["Department"] == "Marketing";

     }


Filtration syntax
-----------------

SharePoint Org Chart allows to filter boxes using JavaScript function. 
This function evaluates data for org chart box and returns a boolean value. 
If "true", then box with such data will be displayed.

Below you can see the snippet for filtration function:

.. code::

    function(itemData, context){

       //You can get field values like this: itemData["Department"]

       return true;

     }


You can use **itemData** input parameter to access data for the current box and verify it. 
Use internal names of properties to access their values like this: itemData[“Department”].

Use typical JavaScript `conditions <http://www.w3schools.com/js/js_if_else.asp>`_ , `comparison operators <http://www.w3schools.com/js/js_comparisons.asp>`_ and functions like `indexOf <http://www.w3schools.com/jsref/jsref_indexof.asp>`_  to verify data. 
For example, you may need to include to org chart only employees from the specific department. 
In this case, the function to display employees from Marketing department looks like this:

.. code::

    function(itemData){

       return itemData["Department"] == "Marketing";

     }


What is Item ID (Root employee)
-------------------------------

Org Chart uses Item ID to find user profiles and list items and organize them properly. 
It is mapped according to the data source your Org Chart is pulling information from and also depending on how you mapped this information. 
If you open Org Chart settings again you’ll see under the “Data source settings” tab that we have two options: SharePoint list and User profiles.


.. image:: /../_static/img/advanced-web-part-configuration/filtration/08-data-souce.jpg
    :alt: Data source


In case you’re using User profiles as the data source, Org Chart will use one’s account name as the Item ID. 
In SharePoint Online account name will be its e-mail address but using OnPremises installation it usually looks like "domain\accountname". 


Otherwise, if you’re using a SharePoint list as the data source for your Org Chart, you’ll have the option to choose which column from the list is going to work as Item ID. It can be anything like title, e-mail address, ID, etc. 
Please, notice that you’ll also have to set up Item parent ID according to Item ID.

.. image:: /../_static/img/advanced-web-part-configuration/filtration/09-field-mapping.jpg
    :alt: Field mapping


You can also specify a root employee to start the hierarchy from. The option is available on Filtration page. Just start typing the employee name and OrgChart will suggest some matching names.


.. image:: /../_static/img/advanced-web-part-configuration/filtration/RootDetection-1.png
    :alt: Root detection




.. Note:: Go to the next step of the advanced configuration wizard `Layout <../configuration-wizard/layout.html>`_ .
     