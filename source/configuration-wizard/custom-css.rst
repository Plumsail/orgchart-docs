Custom CSS
===========

The Org Chart allows to specify custom CSS styles. If you are familiar with `CSS <http://www.w3schools.com/css/>`_ , you can adjust visualization of company structure to your brand book.

On the picture below you can see example of CSS style which changes the background of boxes to black:

.. image:: /../_static/img/advanced-web-part-configuration/custom-css/OrgChart-Configuration-Wizard-11.png
    :alt: Custom css

You can change the background of the person’s box to black using CSS like this:

.. code-block:: css

  .poch-web-part .pl-item .pl-item-template{
    background-color: black;
    border-color: black;
  }

And this is another example which resizes Org Chart boxes to smaller size. 
Thus, more boxes can be displayed in the single screen.

.. code-block:: css

  /*Width of the box*/
  .poch-web-part .poch-control .pl-item {
    width: 170px;
  }

  /*Font size for the fields in the box*/
  .pl-item-card .field-container {
    font-size: 12px;
  }

  /*Font size for the header field in the box (the first in the box)*/
  .pl-item-card .field-container.header-field {
    font-size: 12px;
  }

  /*Width of the photo in the box*/
  .pl-item-photo img {
    max-width: 42px;
  }

Review more articles on customizing Org Chart look:

- `Customize box HTML template and CSS styles <../how-tos/customize-box-html-template-and-css-styles.html>`_
- `Custom styles for printed Org Chart <../how-tos/custom-printing-css.html>`_

.. Note:: Go to the next step of the advanced configuration wizard `Reset configuration <reset-configuration.html>`_.