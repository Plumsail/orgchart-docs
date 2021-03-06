General settings
====================

This step of `the configuration wizard <run-configuration-wizard.html>`_ allows you to:

.. contents::
   :local:
   :depth: 1

This is how it looks:

.. image:: /../_static/img/advanced-web-part-configuration/general-settings/OrgChart-Configuration-Wizard-5.png
    :alt: OrgChart general settings

Choose predefined skin
----------------------

To change the skin of the Organization Chart choose it from combo box. 
There are two skins adopted for mobile devices BlackMetroTouch and MetroTouch, 
they have large expand buttons to simplify touch navigation, all skins support dragging of the visible area with touch.


List of available skins:

- Modern
- Forest
- Office
- Sunset

- Black
- Glow
- Office Black
- Vista

- BlackMetroTouch
- Hay
- Office Blue
- Web 2.0
   
- Light Gray
- Metro
- Outlook
- Web Blue
   
- Silver
- MetroTouch
- Simple
- Windows 7
- Silk
        

Set number of visible tree levels
-----------------------------

You can also control a number of levels visible by default. Use input **Number of visible tree levels** to change it. 
You may expand all hierarchy tree by default, just set a value large enough in the input, for example 1000.

.. Note:: this can affect performance of Org Chart on large structures.


Enable / disable zoom
---------------------

You can use mouse wheel to zoom in and zoom out in the Org Chart web part. To disable/enable this functionality use *Enable zoom* checkbook.


Display employee level number
-----------------------------

Also, you can display the level number in your hierarchy tree for each user by checking **Display level number**.


Display number of solid line reports
------------------------------------

You can enable the feature for displaying the number of solid line reports for all users in your structure by checking *Display number of solid line reports*.
  

Configure search only in indexed list columns
---------------------------------------------

If it is enabled Org Chart searches only in `indexed list columns <https://support.office.com/en-us/article/add-an-index-to-a-sharepoint-column-f3f00554-b7dc-44d1-a2ed-d477eac463b0>`_. 
It is required if there are more than 5000 items in a list and list view threshold breaks items search.


Configure vacancies
-------------------

.. Note:: If vacancies don’t appear in your web part try to `clear cache <../how-tos/data-caching.html>`_. Also, vacancies are not supported in SharePoint 2010 version.

Vacancies are stored in a separate SharePoint list. A list will be created automatically at specified **Vacancies list URL**. 
Once you enabled vacancies **Manage vacancies** menu item will appear:

.. image:: /../_static/img/advanced-web-part-configuration/general-settings/ManageVacanciesMenu-1.png
    :alt: Manage vacancies menu

This menu item redirects user to vacancies list. To create new vacancies, create new list item and specify **Manager**. 
It can be account name for **User Profiles** data source and list item ID for **SharePoint list** data source:

.. image:: /../_static/img/advanced-web-part-configuration/general-settings/CreateVacancy.png
    :alt: Create vacancy

.. Note:: Go to the next step of the advanced configuration wizard `Box template <../configuration-wizard/box-template.html>`_.
