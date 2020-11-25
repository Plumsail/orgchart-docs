Installation for Office 365
===========================

.. contents:: Contents
   :local:
   :depth: 1


Installation
------------

`Download the add-in <https://plumsail.com/sharepoint-orgchart/download/>`_  from our website.

Org Chart is a `SharePoint Framework <https://docs.microsoft.com/en-us/sharepoint/dev/spfx/sharepoint-framework-overview>`_ add-in that allows you to visualize organization structure on both classic and modern SharePoint pages. Unfortunately, SharePoint Store doesn’t support the installation of SharePoint Framework add-ins. That is why you need to install add-in manually.

You have to be a SharePoint administrator to complete the installation. If you don’t see some menus from the instruction below, most likely you are not a SharePoint administrator. Please contact your administrator to assist with the installation.

Navigate to SharePoint Admin Center:

.. image:: /../_static/img/getting-started/installation-office365/OpenSharePointAdminCenter.png
    :alt: Admin center

Go to 'More features' - 'Apps'

.. image:: /../_static/img/getting-started/installation-office365/OpenSharePointApps.png
    :alt: SharePoint Apps

Open **App catalog**:

.. image:: /../_static/img/getting-started/installation-office365/OpenAppCatalog2.png
    :alt: App catalog

If you don’t have **App Catalog** yet, you will be able to create a new one:

.. image:: /../_static/img/getting-started/installation-office365/CreateAppCatalog1.png
    :alt: Create App catalog

Just fill in **Title**, **Web Site Address**, **Administrator** and **Storage Quota** and click **OK**. For example:

- Title – App Catalog Site
- Web Site address – AppCatalog
- Administrator – Fill in your account name
- Storage Quota – 10 GB


.. image:: /../_static/img/getting-started/installation-office365/CreateAppCatalogSiteCollection.png
    :alt: Create App catalog site collection

Navigate to **Apps for SharePoint** and upload Add-in package that you downloaded at the beginning of this instruction (you need to upload to the App Catalog the whole :code:`.sppkg` file without unpacking it):

.. image:: /../_static/img/getting-started/installation-office365/UploadAppToCatalog.png
    :alt: Upload app to catalog

You need to select "Make this solution available to all sites in the organization" in the dialog. Once you did this you can add a web part to a page.

.. image:: /../_static/img/getting-started/installation-office365/orgchart-trust.png
    :alt: OrgChart trust

If you don’t want to make this app availalbe on all sites, you will need to `add app to each site manually <install-add-site-want-add-org-chart.html>`_.

Adding web part to a page
-------------------------

Navigate to the page where you want to add an org chart.

.. note:: If you use "Classic" SharePoint pages follow this  `instruction <add-org-chart-to-classic-page.html>`_  to add web part to a page.

Pick **Plumsail Org Chart** web part from the menu to add it to your page:

.. image:: /../_static/img/getting-started/installation-office365/addWepartModern.png
    :alt: Add web part

Once you added the web part you can `configure it <../getting-started/quick-configuration.html>`_.


Update
------

1. `Download the add-in <https://plumsail.com/sharepoint-orgchart/download/>`_  from our website.

2. Navigate to **Apps for SharePoint** and upload Add-in package that you downloaded at the beginning of this      instruction (you need to upload to the App Catalog the whole :code:`.sppkg` file without unpacking it):

.. image:: /../_static/img/getting-started/installation-office365/UploadAppToCatalog.png
    :alt: Upload app to catalog

3. The package version will be updated after that.
