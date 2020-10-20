Majority of the options in the configuration wizard is filled with default values, you have to configure data source only (first step), then go through the wizard and click **Finish** button.

You can choose between two data sources:

1. SharePoint list.
2. User profiles.

If you choose **User profiles** as a data source, no additional configuration is needed, just go through the wizard until the end. To understand how Org Chart communicates with User profiles service, read `this blog article <../how-tos/additional-resources/how-orgchart-pulls-data-from-ad-on-premises.html>`_.

If you choose **SharePoint list** as a data source, it will be configured to create a new list with demo data by default. You only need to fill **List name**.

.. image:: /../_static/img/getting-started/quick-configuration/CreateNewList.png
    :alt: Create new list

If you want to use an existing SharePoint list, you can choose it from combo box. Then you will have to specify mapping for list fields required for building correct hierarchy. The interface for mapping looks like this.

.. image:: /../_static/img/getting-started/quick-configuration/ConfiguredListFiedsMapping.png
    :alt: Configured list fields mapping

Mapping defines the connection between Organization Chart field and List field. Data from the corresponding list field will be used by the Organization Chart, for example, you can specify the mapping between **Item ID** and list item ID.

**Item ID**, **Item parent ID** and **Display text** mappings are required, you can leave other mappings empty. Once you configured it, you can go through the wizard and click the finish button.

**Item ID** and **Item parent ID** are used to build hierarchy. **Display text** is used as display text for entities in the org chart. For example, you will see **Display text** in the breadcrumb.

You can change these settings later too as you want, but these settings are available for Full Control users only.

Read `Advanced Web Part configuration <../configuration-wizard/data-source-configuration.html>`_ for more information.