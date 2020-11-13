How to display assistants
=========================

This article describes how to display assistants with the help of `Plumsail Org Chart <https://plumsail.com/sharepoint-orgchart/>`_ for SharePoint 2019 / 2016 / 2013 and SharePoint Online in Office 365.

This is how assistants look in "Classic top to bottom" layout. They may be positioned in a different way in other `layouts <../configuration-wizard/layout.html>`_ .

Single assistant

.. image:: /../_static/img/how-tos/display-different-types-of-employees/display-assistant-in-sharepoint-orgchart/org-chart-assistants.png
    :alt: OrgChart assistants


Multiple assistants

.. image:: /../_static/img/how-tos/display-different-types-of-employees/display-assistant-in-sharepoint-orgchart/multiple-assistants.png
    :alt: Multiple assistants


Org Chart supports two data sources: SharePoint list and User Profiles. Let’s see how to configure assistants for each data source.


Display assistants for SharePoint user profiles data source

- :ref:`user-profiles-single-assistant`
- :ref:`user-profiles-multiple-assistants`


Display assistants for SharePoint list data source

- :ref:`sharePoint-list-single-assistant`
- :ref:`sharePoint-list-multiple-assistants`


Display assistants for SharePoint user profiles data source
-----------------------------------------------------------

.. _user-profiles-single-assistant:

.. rubric:: Single assistant

Assistants are enabled by default and you can see that "Assistant" user profile mapping is specified:

.. image:: /../_static/img/how-tos/display-different-types-of-employees/display-assistant-in-sharepoint-orgchart/org-chart-enable-assistants.jpg
    :alt: Enable assistants


Org Chart uses the standard SharePoint "Assistant" user profile property to get information about the assistant of an employee. If you store information about assistants in a separate property, you can change this mapping here.

If you want to disable assistants, just pick **None** in the **Assistant** mapping on this step.


.. _user-profiles-multiple-assistants:

.. rubric:: Multiple assistants

By default, Org Chart uses standard "Assistant" property from SharePoint user profiles. 
It allows you to specify only one assistant per employee. 
If you want to specify multiple assistants per employee, 
you need to create `a new custom user profile property <https://docs.microsoft.com/en-us/sharepoint/administration/add-edit-or-delete-custom-properties-for-a-user-profile>`_ and specify it in the Org Chart mapping.


.. image:: /../_static/img/how-tos/display-different-types-of-employees/display-assistant-in-sharepoint-orgchart/assistants-up-property.png
    :alt: User profiles properties

.. image:: /../_static/img/how-tos/display-different-types-of-employees/display-assistant-in-sharepoint-orgchart/chart-mapping.png
    :alt: Chart mapping

Once you have a new property for assistants, you can fill it with **semicolon separated** list of assistants. 
Also, you may need to `clear Org Chart cache <../how-tos/data-caching.html>`_ to load fresh data.

Example: :code:`assist1@contoso.com; assist2@contoso.com; assist3@contoso.com`

.. image:: /../_static/img/how-tos/display-different-types-of-employees/display-assistant-in-sharepoint-orgchart/field-values.png
    :alt: Field values


Display assistants for SharePoint user profiles data source
-----------------------------------------------------------

.. _sharePoint-list-single-assistant:

.. rubric:: Single assistant

First of all, you need to create a column in your SharePoint list that will store the ID of an assistant. 
Type of this column has to be the same as `an employee id <../configuration-wizard/filtration.html>`_ . 
Then you need to `configure mappings <../configuration-wizard/data-source-configuration.html>`_ of Org Chart fields to columns in your list:

.. image:: /../_static/img/how-tos/display-different-types-of-employees/display-assistant-in-sharepoint-orgchart/org-chart-list-assistant-mapping.jpg
    :alt: Field values

.. _sharePoint-list-multiple-assistants:

.. rubric:: Multiple assistants

If you want to add support for multiple assistants per an employee you have two options:

1. Create a multivalue lookup instead of regular lookup. This will allow you to pick multiple assistants using lookup filed.
2. Or create a regular "Single line of text" list column. This will allow you to specify a semicolon separated list of assistants.

Examples:

- :code:`1; 2; 14; 18` if you use numbers as employee IDs.

- :code:`assist1@contoso.com; assist2@contoso.com; assist3@contoso.com` if you use email addresses (account names) as employee IDs.

3. Map Assistant ID in OrgChart settings to the newly created column.
4. `Clear Org Chart cache <../how-tos/data-caching.html>`_ to load fresh data.

Conclusion
----------

That is all! Now you know how to display structure with single and multiple asistants in SharePoint Org Chart.