Org Chart data caching
======================

Plumsail Org Chart uses client-side caching to improve performance.

Once you open the web part for the first time and navigate over boxes, they are cached in your browser for 24 hours. That is why you may not see modifications you did to your data source. In this case just clear cache using the menu item at the top right corner of the web part:

.. image:: /../_static/img/how-tos/additional-resources/data-caching/OrgChartClearCacheMenu.png
    :alt: OrgChart cache


It is actual for vacancies and dotted line managers as well as for employee properties.

You can change default caching period using `JavaScript framework <../javascript-framework/introduction.html>`_. Pay attention to `renderer.config.clientSideCachingLifeDays <../javascript-framework/configuration.html#client-side-caching-life-days>`_ property. You can put custom JavaScript code into the code editor of the `configuration wizard <../configuration-wizard/custom-javascript.html>`_.