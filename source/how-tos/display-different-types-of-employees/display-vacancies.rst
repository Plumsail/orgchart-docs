Add Org Chart to Teams tabs
===========================


Did you know that you can use the `Plumsail Org Chart <https://plumsail.com/sharepoint-orgchart/>`_ in Teams? With an organizational chart in Teams, you can see who people you are communicating with report to and who reports to them. 
You can also search for other people while you are there and see their position in the organization.

There are two simple steps to add Plumsail Org Chart to a Teams tab:

- First, add Org Chart to a page in the team’s site
- Then, create a Teams tab with this page in it.

Let’s see how to do it.


Adding Org Chart to the team’s site
-----------------------------------

Navigate to the team’s site:

.. image:: /../../_static/img/how-tos/ms-teams/navigate-to-the-team-site.png
    :alt: Team site


Go to the Site Pages:

.. image:: /../../_static/img/how-tos/ms-teams/site-pages.png
    :alt: Site pages


Create a new page and pick Plumsail Org Chart web part from the menu to add it to your page:

.. image:: /../../_static/img/how-tos/ms-teams/add-web-part.png
    :alt: Add wen part


Follow the instruction to `configure </../../configuration-wizard/run-configuration-wizard.html>`_ Org Chart.

If you want Org Chart to occupy full screen by default, add the following code into the Custom JavaScript tab:

.. code::

   renderer.fullSizeToggle();


.. image:: /../../_static/img/how-tos/ms-teams/full-size-toggle-1.png
    :alt: Full site toggle


Adding Org Chart to a Teams tab
-------------------------------

Create a new tab, choose SharePoint option in the popup, and then pick the page with the Org Chart web part in it:

.. image:: /../../_static/img/how-tos/ms-teams/create-tab.png
    :alt: Create tab


.. image:: /../../_static/img/how-tos/ms-teams/tab-type.png
    :alt: Tab type


.. image:: /../../_static/img/how-tos/ms-teams/org-chart-page.png
    :alt: OrgChart


That is it. Now, your Org Chart is displayed in the Teams tab:

.. image:: /../../_static/img/how-tos/ms-teams/teams-tab-compact.png
    :alt: Team tab