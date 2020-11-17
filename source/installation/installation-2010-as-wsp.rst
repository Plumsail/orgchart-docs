Installation of Org Chart for SharePoint 2010 as WSP package
============================================================

`Download wsp-package <https://plumsail.com/sharepoint-orgchart/download/>`_ and place it to one of the servers in your Sharepoint 2010 farm. Run **Sharepoint 2013 Management Shell** as administrator:

.. image:: /../_static/img/getting-started/installation-2010-as-wsp/RunAsAdmin.gif
    :alt: Run as administrator

Print :code:`Add-SPSolution`:

.. image:: /../_static/img/getting-started/installation-2010-as-wsp/OrgChartPowerShellAddSolution2010.png
    :alt: Power Shell add solution 

Open **Central Administration as administrator** > **System Settings** > **Manage farm solutions**. Select :code:`plumsail.orgchart.wsp` and press **Deploy Solution** link:

.. image:: /../_static/img/getting-started/installation-2010-as-wsp/OrgChartDeploy2010.png
    :alt: Deploy solution

Go to your application. Select **Site Settings** item in the root of the site collection. Choose **Site collection features** in **Site Collection Administration** section:

.. image:: /../_static/img/getting-started/installation-2010-as-wsp/SiteCollectionFeatures2010.png
    :alt: Site collection features

Activate **Plumsail Org Chart** feature.

.. image:: /../_static/img/getting-started/installation-2010-as-wsp/OrgChartFeature2010.png
    :alt: Org Chart feature

Next step is to `add web part to a page <sharepoint2010.html#add-web-part>`_.