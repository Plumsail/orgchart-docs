Display dotted-line managers
============================


In this article, I want to show you how to display dotted-line reports in `Plumsail Org Chart <https://plumsail.com/sharepoint-orgchart/>`_. 
It is quite a common scenario for companies with a matrix organization structure when there are direct managers and dotted-line managers.


As Plumsail Org Chart displays hierarchy, but not matrix, 
it is important to understand how dotted-line reports appear in the visualization. 
Please take a look at the example below.

.. image:: /../../_static/img/how-tos/display-different-types-of-employees/display-dotted-line-managers/OrgChartDottedlinesExample.png
    :alt: Dotted-lines managers example


Org Chart supports two data sources, SharePoint list, and User Profiles. Each data source has some specifics in the configuration of dotted-line managers. Let us move step by step.

.. note:: Org Chart allows you to specify one or more dotted-line managers for an employee. Thus, a single employee may have a single direct (solid line) manager and an unlimited number of dotted-line managers.

If a solid line employee has a dotted-line manager, there will be displayed a small button next to the solid line box. It allows you to quickly navigate from the solid box to a dotted-line manager. If the employee have more than one dotted-line manager, you will navigate to the first one specified in the corresponding field.

.. image:: /../../_static/img/how-tos/display-different-types-of-employees/display-dotted-line-managers/dotted-lines-navigation.jpg
    :alt: Dotted lines navigation


This article has two parts:

- :ref:`dotted-line-managers-for-user-profiles`
- :ref:`dotted-line-managers-for-sharepoint-list`


.. _dotted-line-managers-for-user-profiles:


Dotted-line managers for User Profiles data source
--------------------------------------------------

Dotted-line managers are enabled for User Profiles data source by default. If you open the configuration wizard on the “Data source settings” step and see that “Dotted manager” mapping is specified, it means that dotted-managers are enabled and Org Chart will try to get data from this user profile property:

.. image:: /../../_static/img/how-tos/display-different-types-of-employees/display-dotted-line-managers/DottedManagersGeneralSettings.png 
    :alt: Settings


If you want to disable dotted line managers, just select “None” for the “Dotted line” manager mapping on the “Data source settings” step.


How to add support for multiple dotted-line managers for User Profiles data source
----------------------------------------------------------------------------------

By default, Org Chart uses standard “Dotted-line Manager” property from SharePoint user profiles. 
It allows you to specify only one dotted line manager per employee. 
If you want to specify multiple dotted-line managers per employee, 
you need to create `a new custom user profile property <https://docs.microsoft.com/en-us/sharepoint/administration/add-edit-or-delete-custom-properties-for-a-user-profile>`_ and specify it in the Org Chart mapping.


Once you have a new property for dotted-line managers, you can fill it with **semicolon separated** list of managers.


Example: manager1@contoso.com; manager2@contoso.com; manager3@contoso.com


Org Chart supports following types of user profile properties, consider it when creating a new user profile property:

- String (Single Value)
- String (Multi Value)
- E-mail
- Person – this type allows you to specify only one value. Thus, if you want support for multiple dotted-line managers, you need to pick some other type.


Configuration for SharePoint 2019 / 2016/ 2013 (On-Premises)
------------------------------------------------------------

If you use SharePoint 2019 / 2016 / 2013 On-Premises, then, no additional configuration required.


Configuration for SharePoint Online in Office 365
-------------------------------------------------


If you use Org Chart for Office 365, additional configuration of SharePoint search service is required. Otherwise, Org Chart will not be able to find subordinates for dotted line managers.

You need to add a managed search property for the user profile property that contains information about dotted-line managers for the user profile. By default, Org Chart uses “Dotted-line Manager” property. It doesn’t have own managed search property. If you have another user profile property, you need to create a managed property for it.

**Important**: The name for the search metadata property has to be **DottedLineManager**.

We prepared an article for you `describing how to create a new search metadata property <https://medium.com/plumsail/how-to-create-managed-search-property-for-user-profiles-in-office-365-as-fast-as-possible-ac4a95cd7afb>`_ . 
Please follow it step by step and create a new property called “DottedLineManager”. 
If you specify another name, Org Chart will not be able to find dotted-line subordinates. 
Be patient, SharePoint search takes time to crawl data and update configuration. 
It may take a few hours or even more before your new managed property is working.


Once your managed property is configured, you may need to `clear Org Chart cache <../additional-resources/data-caching.html>`_ to load fresh data.


.. _dotted-line-managers-for-sharepoint-list:


Dotted-line managers for SharePoint List data source
----------------------------------------------------

If you choose the SharePoint List data source, you need to specify mappings of list columns and Org Chart properties in the ‘Data source’ step of the configuration wizard:

.. image:: /../../_static/img/how-tos/display-different-types-of-employees/display-dotted-line-managers/org-chart-list-dotted-managers-config.jpg
    :alt: Settings


In my case, I use the standard list item ID column as an ID of an employee. 
And I also created a separate column to store information about the dotted-line manager for an employee. 
I used Lookup column which looks to the same list with employees. 
Thus, I can pick any other employee from a list on the list item edit form. 
You can see the configuration for the column below:

.. image:: /../../_static/img/how-tos/display-different-types-of-employees/display-dotted-line-managers/DottedLineManagerColumn.jpg
    :alt: Dotted-line managers column

Thus, I created a separate column for a dotted-line manager and specified it in the mapping of the configuration wizard.

You would use another type of column, for example, string, but I decided to use Lookup to improve the user experience.


How to add support for multiple dotted-line managers per employee for SharePoint list data source
-------------------------------------------------------------------------------------------------

If you want to add support for multiple dotted-line managers per an employee you have two options:

1. Create a multivalue lookup instead of regular lookup. This will allow you to pick multiple dotted-line managers using lookup filed.

2. Or create a regular “Single line of text” list column. This will allow you to specify a semicolon separated list of dotted-line managers.

Examples:

- 1; 2; 14; 18 if you use numbers as employee IDs.
- manager1@contoso.com; manager2@contoso.com; manager2@contoso.com if you use email addresses (account names) as employee IDs.

Conclusion
----------

That is all! Now you know how to display structure with dotted-line managers in SharePoint Org Chart.