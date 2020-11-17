How to order employees boxes using a custom field for Org Chart in SharePoint and Microsoft Teams
=================================================================================================

You can choose a custom field for ordering the employees boxes in your chart. 
It can be an existing field or a new one. 
If you use Users Profiles as a data source you can create a new user property. 
In case you use a list, you can create a new list column.

To define the sorting rules, please, add a code like this to the Custom JavaScript step of the Configuration Wizard:

.. image:: /../_static/img/how-tos/filter-and-order-boxes/order-employees-boxes-using-a-custom-field/sorting.png
    :alt: Sorting

.. code-block:: javascript
  
  renderer.config.nodesSortOrder = "ASC";
  renderer.config.nodesSortFieldName = "SortingFieldName";


- :code:`nodesSortOrder` – a sorting order, for example, :code:`ASC` or :code:`DESC`.


- :code:`nodesSortFieldName` – the internal name of a list field or a property from the User Profile service.

Currently, Org Chart handles all the properties as strings, so you should not use numbers for defining the sorting order.