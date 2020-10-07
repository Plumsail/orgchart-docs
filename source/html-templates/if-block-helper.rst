The if block helper
===================

You can use the **if** helper to conditionally render a block. If its argument returns false, undefined, null, ” or [] (a “falsy” value), Handlebars will not render the block.

.. code::

   <div>  
   {{#if PictureURL}}
     <img src="{{PictureURL}}" alt="" />
   {{/if}}
   </div>  
   </pre>


If you need to build **if/else** behavior you can add **else** block like this:

.. code::

   <div>  
    {{#if PictureURL}}
      <img src="{{PictureURL}}" alt="" />
    {{else}}
      No picture
    {{/if}}
   </div>


.. note:: check out next part of HTML templates `The unless block helper <unless-block-helper.html>`_ .