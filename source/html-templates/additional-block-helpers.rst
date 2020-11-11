Additional block helpers
========================

We added two new helpers into Handlebars framework.

The **safeImage** block allows inserting of an **img** tag into HTML markup which will handle broken pictures and hide them. 
This is how you can use it:

.. code::

   {{safeImage PictureURL}}


Where **PictureURL** is an internal name of a field with URL.


The **detailsTooltipLink** block allows wrapping of some HTML content with **a** tag which will show details tooltip once you click on it. 
We use this block in the box template.

.. code::

   {{#detailsTooltipLink}}
   {{PreferredName}}
   {{/detailsTooltipLink}}

Where PreferredName could be an internal name of a field.

You also can add other HTML content inside this block:

.. code::

   {{#detailsTooltipLink}}
     Some HTML content
   {{/detailsTooltipLink}}


.. note:: check out next part of HTML templates `Structure of the context object <structure-of-the-context-object.html>`_ .