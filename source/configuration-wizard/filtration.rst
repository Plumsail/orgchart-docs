Filtration
===========

.. contents:: Contents
   :local:
   :depth: 1

Here is how the filtration step of `the configuration wizard <run-configuration-wizard.html>`_ looks:

.. image:: /../_static/img/advanced-web-part-configuration/filtration/OrgChart-Configuration-Wizard-3.png
    :alt: Filtration

Start structure from employee
-----------------------------

You can start the hierarchy from a specific employee. Just start typing the employee name. Org Chart will suggest some matching names.

You can leave the starting employee field empty. In this case:

- If you use User profiles, the starting employee will be found based on current user relations. Org CHart will find the current user. Then it will traverse up by manager relation until it finds an employee without a manager. This person will be a starting employee.
- If you use a SharePoint list, the first employee without a manager will be a starting employee.

Filter employees
----------------

Check `this article <../how-tos/filter-and-order-boxes/filter-orgchart-by-department.html>`_ for example on filtration employees by department. You can use the filtration rule to exclude people from the chart or show just specific departments or employees. You may filter by department, name, or by any other field from your data source

SharePoint Org Chart allows filtering boxes using JavaScript function. This function evaluates data for the org chart box and returns a boolean value. If "true", then a box with such data will be displayed.

You can use **itemData** input parameter to access data for the current box and verify it. Use internal names of properties to access their values like this: :code:`itemData["Department"]`.

Use typical JavaScript `conditions <http://www.w3schools.com/js/js_if_else.asp>`_, `comparison operators <http://www.w3schools.com/js/js_comparisons.asp>`_, and functions like `indexOf <http://www.w3schools.com/jsref/jsref_indexof.asp>`_ to verify data. For example, you may need to include in the org chart only employees from the specific department. In this case, the function to display employees from the Marketing department looks like this: 

.. code-block:: javascript

    function(itemData){

       return itemData["Department"] == "Marketing";

     }

And with this filter, you can exclude all employees whose name contains Smith:

.. code-block:: javascript

  return !itemData["PreferredName"].contains("Smith");

.. Note:: Go to the next step of the advanced configuration wizard `Layout <../configuration-wizard/layout.html>`_.
     