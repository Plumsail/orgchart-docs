Support of search in a list with more than 5000 items
=====================================================

In this article I will show how to add support of search in a list with more than 5000 items for `Plumsail Org Chart <https://plumsail.com/sharepoint-orgchart/>`_ . 
By default, SharePoint prohibits tasks that cause excessive server load. 
Therefore, we need to index the columns where OrgChart should be able to search elements. 
This is our first thing to do.

1. Go to Site content -> List settings.

.. image:: /../../_static/img/how-tos/other-examples/support-of-search-in-a-list-with-more-than-5k-items/ListSettings.png
    :alt: List Settings

2. Find and click on Indexed columns.

.. image:: /../../_static/img/how-tos/other-examples/support-of-search-in-a-list-with-more-than-5k-items/IndexedColumns.png
    :alt: Indexed Columns

3. Click on ‘Create a new Index’ and select a column you’d like to be indexed and used in OrgChart search

.. image:: /../../_static/img/how-tos/other-examples/support-of-search-in-a-list-with-more-than-5k-items/CreateIndex.gif
    :alt: Create Index

Once it’s done we’re heading to OrgChart settings.

4. Open OrgChart settings, enable ‘Search only in indexed list columns’ option and specify the Root ID. Without Root ID the standart search algorithm won’t be able to work wth the List.

.. image:: /../../_static/img/how-tos/other-examples/support-of-search-in-a-list-with-more-than-5k-items/OrgChartSettings.png
    :alt: OrgChart Settings

.. image:: /../../_static/img/how-tos/other-examples/support-of-search-in-a-list-with-more-than-5k-items/OrgChartSettings2.png
    :alt: OrgChart Settings


Conclusion
----------

That is all. Now OrgChart can search in the SharePoint list with more than 5000 items. 
If you didn’t install it yet, `download <https://plumsail.com/sharepoint-orgchart/download/>`_ it and follow the installation instruction for your version of SharePoint in the `documentation <../../configuration-wizard/run-configuration-wizard.html>`_. 
It is quite easy to get started.