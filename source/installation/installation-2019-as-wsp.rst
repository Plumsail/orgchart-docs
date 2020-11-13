Installation of Org Chart for SharePoint 2019 as WSP package
============================================================

The installation process consists of two parts:

- Install services – web part will pull data from them.
- Install SharePoint Framework add-in – it is a web part itself.

`Download wsp-package <https://plumsail.com/sharepoint-orgchart/download/>`_ and extract it from the downloaded zip archive. The archive contains wsp-package (:code:`Plumsail.OrgChart.2019.wsp`) and SharePoint Framework package (:code:`plumsail-orgchart-sp-2019.sppkg`). Place those files to one of the servers in your Sharepoint 2019 farm.

Install services
----------------

Run Sharepoint 2019 Management Shell as administrator:

.. image:: /../_static/img/getting-started/installation-sharepoint2019/managementShell2019.png
    :alt: Management shell 2019

.. image:: /../_static/img/getting-started/installation-sharepoint2019/WspInstallation2.png
    :alt: WSP installation

Print  :code:`Add-SPSolution [path to wsp-package]` :

.. image:: /../_static/img/getting-started/installation-sharepoint2019/WspInstallation2.png
    :alt: WSP installation

Open Central Administration as administrator and navigate to **System Settings** → **Manage farm solutions**. Select :code:`plumsail.orgchart.2019.wsp` and press **Deploy Solution** link:

.. image:: /../_static/img/getting-started/installation-sharepoint2019/SolutionProperties.png
    :alt: Solution properties

Install SharePoint Framework add-in
-----------------------------------

Run SharePoint 2019 Central Administration as administrator on your server.

.. image:: /../_static/img/getting-started/installation-sharepoint2019/ca2019.png
    :alt: Central Administration

Navigate to Apps -> Manage App Catalog

.. image:: /../_static/img/getting-started/installation-sharepoint2019/manageAppCatalog2019.png
    :alt: Manage app catalog 2019

Navigate to **Apps for SharePoint** and upload Add-in package that you downloaded at the beginning of this instruction:

.. image:: /../_static/img/getting-started/installation-sharepoint2019/UploadAppToCatalog2019.png
    :alt: Upload app to catalog 2019

You need to select "Make this solution available to all sites in the organization" in the dialog. Once you did this you can add a web part to a page.

.. image:: /../_static/img/getting-started/installation-sharepoint2019/orgchart2019-trust.png
    :alt: OrgChart 2019 trust

If you don’t want to make this app availalbe on all sites, you will need to `add app to each site manually <install-add-site-want-add-org-chart.html>`_ .

Adding web part to a page
-------------------------

.. note:: If you use "Classic" SharePoint pages follow this `instruction <add-org-chart-to-classic-page.html>`_ to add web part to a page.

Navigate to the page where you want to add an org chart.

Pick **Plumsail Org Chart** web part from the menu to add it to your page:

.. image:: /../_static/img/getting-started/installation-sharepoint2019/addWepartModern.png
    :alt: Add web part

Once you added the web part you can `configure it <../getting-started/quick-configuration.html>`_.