Data source configuration
=========================

This is the first step of `the configuration wizard <run-configuration-wizard.html>`_.

Org Chart can pull employees information from two data sources:

1. SharePoint list
2. User profiles

If you choose **User profiles** as a data source, no additional configuration of data source is needed, just go through the wizard until the end. 
Unless you want to configure `dotted-line managers <../how-tos/display-different-types-of-employees/display-dotted-line-managers.html>`_ or configure `assistants <../how-tos/display-different-types-of-employees/display-assistant-in-sharepoint-orgchart.html>`_.

To understand how Org Chart communicates with User profiles service, read `the blog article <../how-tos/additional-resources/how-orgchart-pulls-data-from-ad-on-premises.html>`_.

If you choose **SharePoint list** as a data source, it will be configured to create a new list with demo data by default. 
You only need to fill **List name**.

.. image:: /../_static/img/advanced-web-part-configuration/data-source-configuration/OrgChart-Configuration-Wizard-1.png
    :alt: OrgChart configuration wizard

If you want to use an existing SharePoint list, you can choose it from combo box. 
Then you will have to specify mapping for list fields required for building correct hierarchy. 
The interface for mapping looks like this.


.. image:: /../_static/img/advanced-web-part-configuration/data-source-configuration/OrgChart-Configuration-Wizard-2.png
    :alt: OrgChart configuration wizard


Mapping defines the connection between Organization Chart field and List field. Data from the corresponding list field 
will be used by the Organization Chart, for example you can specify mapping between **Employee ID** and list item ID.

**Employee ID**, **Manager ID** and **Display text** mappings are required, you can leave other mappings empty. 
Once you configured it, you can go through the wizard and click the finish button.

**Employee ID** and **Manager ID** are used to build hierarchy. **Display text** is used as display text for entities in the org chart. 
For example you will see "Display text" in the breadcrumb.


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
        - This mapping defines where information about assistant is stored for current item. This is optional mapping. Please read `this instruction <../how-tos/display-assistant-in-sharepoint-orgchart.html>`_ to learn how to configure assistants.
   
    *   - Dotted manager ID
        - This is unique ID of dotted-line manager. For example, it could be ID of manager or login of manager. Type of this field should be the same as type of **Manager ID**. Please read `this instruction <../how-tos/display-dotted-line-managers.html>`_ to learn how to configure dotted-line managers.

    
.. rubric:: Support of search in a list with more than 5000 items

SharePoint has a standard restriction on SharePoint list item queries in 5000 items. 
To be able to use search in such list you need to index the columns on the list level and also enable option **Search only in indexed list columns** in OrgChart settings. 
You can find more information about it in `this article <../how-tos/other-examples/support-of-search-in-a-list-with-more-than-5k-items.html>`_.


.. Note:: Go to the next step of the advanced configuration wizard `Filtration <../configuration-wizard/filtration.html>`_.
           