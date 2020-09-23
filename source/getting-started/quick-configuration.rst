Quick configuration
===================

.. note:: If after configuration of the web part you did some changes and they don’t appear in the web part try to clear cache (link).

Once you added the web part to your page, you can see the message asking you to configure the web part.

Org Chart for Office 365 or for SharePoint 2019 and modern SharePoint pages
---------------------------------------------------------------------------

1. Open your page in edit mode
2. Click ‘pencil’ icon at the left side of your web part. It will open property pane.

.. image:: /../_static/img/getting-started/quick-configuration/pencil-icon.png
    :alt: Configuration



3. Click ‘Open Config Wizard’ in the property pane.


Org Chart for Office 365 or for SharePoint 2019 and classic SharePoint pages
----------------------------------------------------------------------------

1. Open your page in edit mode
2. Open web part properties

.. image:: /../_static/img/getting-started/quick-configuration/EditClassicWebPart.png
    :alt: Edit classic web part

3. Click *Configure*
4. Click *Open Config Wizard*
5. Don’t forget to click *Ok* to apply changes after completing configuration.

Org Chart for SharePoint 2010/2013/2016 On-Premises
---------------------------------------------------

Just click on the ‘click here’ link inside the web part.

.. image:: /../_static/img/getting-started/quick-configuration/OpenWizardFromMessage.png
    :alt: Open wizard from message

Majority of the options in the configuration wizard is filled with default values, you have to configure data source only (first step), then go through the wizard and click *Finish* button.

You can choose between two data sources:

1. SharePoint list.
2. User profiles.

If you choose *User profiles* as a data source, no additional configuration is needed, just go through the wizard until the end. To understand how Org Chart communicates with User profiles service, read this blog article (link).

If you choose *SharePoint list* as a data source, it will be configured to create a new list with demo data by default. You only need to fill *List name*.

.. image:: /../_static/img/getting-started/quick-configuration/CreateNewList.png
    :alt: Create new list

If you want to use an existing SharePoint list, you can choose it from combo box. Then you will have to specify mapping for list fields required for building correct hierarchy. The interface for mapping looks like this.

.. image:: /../_static/img/getting-started/quick-configuration/ConfiguredListFiedsMapping.png
    :alt: Configured list fields mapping

Mapping defines the connection between Organization Chart field and List field. Data from the corresponding list field will be used by the Organization Chart, for example, you can specify the mapping between *Item ID* and list item ID.

*Item ID*, *Item parent ID* and *Display text* mappings are required, you can leave other mappings empty. Once you configured it, you can go through the wizard and click the finish button.

*Item ID* and *Item parent ID* are used to build hierarchy. *Display text* is used as display text for entities in the org chart. For example, you will see *Display text* in the breadcrumb.

You can change these settings later too as you want, but these settings are available for Full Control users only.

Read `Advanced Web Part configuration <../configuration-wizard/run-configuration-wizard.html>`_ for more information.