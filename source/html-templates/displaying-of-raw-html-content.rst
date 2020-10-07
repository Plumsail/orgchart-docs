Displaying of raw HTML content
==============================

Handlebars template engine escapes HTML tags by default. In the case you want to add to the box template a property which contains the ones, you should enclose it in triple braces.


.. code::

   {{{AboutMe}}}


For example, you want to display the “About me” property from SharePoint user profiles on the tooltip. If you just add it to the tooltip template, you will get an alike result with escaped HTML tags.

In this case, you need to enclose the “AboutMe” token into triple braces.

As a result, the mark-up of the content will be properly processed:


.. image:: /../_static/img/html-templates/HTML_Escaped.png
    :alt: HTML Escaped


.. note:: check out next part of HTML templates `Additional block helpers <additional-block-helpers.html>`_ .