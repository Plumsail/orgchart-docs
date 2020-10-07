HTML templating syntax description
==================================

We use `Handlebars <http://handlebarsjs.com/>`_ templating engine to render boxes, tooltips and search results. 
You can specify custom HTML templates using Handlebars syntax to change look and feel of the Org Chart.

You can customize templates using the configuration wizard. 
Read `Advanced Web Part configuration <../configuration-wizard/run-configuration-wizard.html>`_ for more information.

You can find a detailed description of Handlebars syntax on the `official site <http://handlebarsjs.com/>`_ . 
In this instruction, we covered only frequently used blocks and our custom blocks, developed for the Org Chart especially.

Handlebars template look like regular HTML, with embedded handlebars expressions.

.. code::

   {{Department}}


A handlebars expression is a {{, some contents, followed by a }}. In the example above you see *{{Department}}* expression. 
It allows rendering of the value of the field with internal name ‘Department’.


Example of the template
------------------------

This is an example of the box template. To understand the meaning of different blocks read description below.

.. code::

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

.. note:: check out next part of HTML templates `The if block helper <if-block-helper.html>`_ .