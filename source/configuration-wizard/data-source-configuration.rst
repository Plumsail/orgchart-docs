Data source configuration
=========================

This is the first step of the wizard.

You can choose between two data sources:

1. SharePoint list
2. User profiles

If you choose ‘User profiles’ as a data source, no additional configuration of data source is needed, just go through the wizard until the end. 
Unless you want to configure dotted-line managers (link) or configure assistants (link).

To understand how Org Chart communicates with User profiles service, read blog article (link).

If you choose *SharePoint list* as a data source, it will be configured to create a new list with demo data by default. 
You only need to fill *List name*.

.. image:: /../_static/img/advanced-web-part-configuration/data-source-configuration/OrgChart-Configuration-Wizard-1.png
    :alt: OrgChart configuration wizard

If you want to use an existing SharePoint list, you can choose it from combo box. 
Then you will have to specify mapping for list fields required for building correct hierarchy. 
The interface for mapping looks like this.


.. image:: /../_static/img/advanced-web-part-configuration/data-source-configuration/OrgChart-Configuration-Wizard-2.png
    :alt: OrgChart configuration wizard


Mapping defines the connection between Organization Chart field and List field. Data from the corresponding list field 
will be used by the Organization Chart, for example you can specify mapping between *Item ID* and list item ID.

*Item ID*, *Manager ID* and *Display text* mappings are required, you can leave other mappings empty. 
Once you configured it, you can go through the wizard and click the finish button.

*Item ID* and *Manager ID* are used to build hierarchy. *Display text* is used as display text for entities in the org chart. 
For example you will see ‘Display text’ in the breadcrumb.


.. rubric:: Description of mappings

.. list-table::
    :header-rows: 1
    :widths: 10 50

    *   - Name
        - Description

    *   - Employee ID
        - This is unique ID of an employee. It can be list item ID, user login or any other unique identifier of the person.
    
    *   - Manager ID
        - This is unique ID of an employee manager. For example it could be ID of manager or login of manager. We need it to build a well-structured tree.
   
    *   - Display text
        - Display text is displayed in the breadcrumbs of the Org Chart.
   
    *   - Assistant ID
        - This mapping defines where information about assistant is stored for current item. This is optional mapping. Please read this instruction (link) to learn how to configure assistants.
   
    *   - Dotted manager ID
        - This is unique ID of dotted-line manager. For example, it could be ID of manager or login of manager. Type of this field should be the same as type of “Manager ID”. Please read this instruction (link) to learn how to configure dotted-line managers.

    
.. rubric:: Support of search in a list with more than 5000 items

SharePoint has a standard restriction on SharePoint list item queries in 5000 items. 
To be able to use search in such list you need to index the columns on the list level and also enable option *Search only in indexed list columns* in OrgChart settings. 
You can find more information about it in this article (link).


.. Note:: Go to the next step of the advanced configuration wizard `Filtration <../configuration-wizard/filtration.html>`_ .
           