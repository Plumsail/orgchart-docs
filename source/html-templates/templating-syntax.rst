HTML templating syntax description
==================================

.. _example-of-template:

.. contents:: Contents
   :local:
   :depth: 1

Introduction
------------

We use `Handlebars <http://handlebarsjs.com/>`_ templating engine to render boxes, tooltips and search results. 
You can specify custom HTML templates using Handlebars syntax to change look and feel of the Org Chart.

You can customize templates using the configuration wizard. 
Read `Advanced Web Part configuration <../configuration-wizard/run-configuration-wizard.html>`_ for more information.

You can find a detailed description of Handlebars syntax on the `official site <http://handlebarsjs.com/>`_. 
In this instruction, we covered only frequently used blocks and our custom blocks, developed for the Org Chart especially.

Handlebars template look like regular HTML, with embedded handlebars expressions.

.. code-block:: html

  {{Department}}


A handlebars expression is a {{, some contents, followed by a }}. In the example above you see *{{Department}}* expression. 
It allows rendering of the value of the field with internal name "Department".


.. _example-of-template:

Example of the template
------------------------

This is an example of the box template. To understand the meaning of different blocks read description below.

.. code-block:: html

  <div class="pl-item-photo">
    {{#if PictureURL}}
      {{#detailsTooltipLink}}
        {{safeImage PictureURL}}
      {{/detailsTooltipLink}}
    {{/if}}
  </div>
  <div class="pl-item-fields">
    <div class="field-container header-field">
      {{#detailsTooltipLink}}
        {{PreferredName}}
      {{/detailsTooltipLink}}
    </div>
    <div class="field-container">{{Title}}</div>
    <div class="field-container">{{Department}}</div>
  </div>

.. _if-block-helper:

The if block helper
-------------------

You can use the :code:`if` helper to conditionally render a block. If its argument returns :code:`false`, :code:`undefined`, :code:`null`, empty string or empty array (a "falsy" value), Handlebars will not render the block.

.. code-block:: html

  <div>
    {{#if PictureURL}}
    <img src="{{PictureURL}}" alt="" />
    {{/if}}
  </div> 


If you need to build :code:`if/else` behavior you can add :code:`else` block like this:

.. code-block:: html

  <div>
    {{#if PictureURL}}
    <img src="{{PictureURL}}" alt="" />
    {{else}}
    No picture
    {{/if}}
  </div>

.. _unless-block-helper:

The unless block helper
-----------------------

You can use the :code:`unless` helper as the inverse of the :code:`if` helper. 
Its block will be rendered if the expression returns a falsy value.

.. code-block:: html

   {{#unless PictureURL}}<h3>WARNING: Picture not found!</h3>{{/unless}}

.. _displaying-of-raw-html-content:

Displaying of raw HTML content
------------------------------

Handlebars template engine escapes HTML tags by default. In the case you want to add to the box template a property which contains the ones, you should enclose it in triple braces.

.. code-block:: html

  {{{AboutMe}}}

For example, you want to display the "About me" property from SharePoint user profiles on the tooltip. If you just add it to the tooltip template, you will get an alike result with escaped HTML tags.

In this case, you need to enclose the :code:`AboutMe` token into triple braces.

As a result, the mark-up of the content will be properly processed:

.. image:: /../_static/img/html-templates/HTML_Escaped.png
    :alt: HTML Escaped

.. _additional-block-helpers:

Additional block helpers
------------------------

We added two new helpers into Handlebars framework.

The :code:`safeImage` block allows inserting of an :code:`img` tag into HTML markup which will handle broken pictures and hide them. 
This is how you can use it:

.. code-block:: html

  {{safeImage PictureURL}}

Where :code:`PictureURL` is an internal name of a field with URL.


The :code:`detailsTooltipLink` block allows wrapping of some HTML content with :code:`a` tag which will show details tooltip once you click on it. 
We use this block in the box template.

.. code-block:: html

  {{#detailsTooltipLink}}
    {{PreferredName}}
  {{/detailsTooltipLink}}

Where PreferredName could be an internal name of a field.

You also can add other HTML content inside this block:

.. code-block:: html

  {{#detailsTooltipLink}}
    Some HTML content
  {{/detailsTooltipLink}}

.. _structure-of-the-context-object:

Structure of the context object
-------------------------------

Handlebars template receives context object, the object which represents data to render. This context object is used to resolve values in the template. The context object is a plain object with multiple fields from a data source:

.. code-block:: javascript

  {
    FieldInternalName1: "FieldValue1",
    FieldInternalName2: "FieldValue2",
    ...
    FieldInternalNameN: "FieldValueN",
  }


Thus, you can access the value of the field with internal name :code:`FieldInternalName1` using such Handlebars expression:

.. code-block:: html

  {{FieldInternalName1}}
