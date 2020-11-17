Installation of Org Chart for SharePoint 2013/2016 as WSP package
=================================================================

`Download wsp-package <https://plumsail.com/sharepoint-orgchart/download/>`_ and place it to one of the servers in your Sharepoint 2013 farm. Run **Sharepoint 2013 Management Shell** as administrator:

.. image:: /../_static/img/getting-started/installation-2013-2016-as-wsp/WspInstallation1.png
    :alt: Run as administrator

.. image:: /../_static/img/getting-started/installation-2013-2016-as-wsp/WspInstallation2.png
    :alt: Run as administrator

Print :code:`Add-SPSolution`:

.. image:: /../_static/img/getting-started/installation-2013-2016-as-wsp/OrgChartPowerShellAddSolution2013.png
    :alt: Power Shell add solution 

Open **Central Administration as administrator** > **System Settings** > **Manage farm solutions**. Select :code:`plumsail.orgchart.wsp` and press **Deploy Solution** link:

.. image:: /../_static/img/getting-started/installation-2013-2016-as-wsp/WspInstallation4.png
    :alt: Deploy solution

Go to your application. Select **Site Settings** item in the root of the site collection. Choose **Site collection features** in **Site Collection Administration** section:

.. image:: /../_static/img/getting-started/installation-2013-2016-as-wsp/WspInstallation5.png
    :alt: Site collection features

Activate **Plumsail Org Chart** feature.

.. image:: /../_static/img/getting-started/installation-2013-2016-as-wsp/WspInstallation6.png
    :alt: Org Chart feature

Next step is to `add web part to a page <sharepoint2013-2016.html#add-web-part>`_.