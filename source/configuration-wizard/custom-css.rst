Custom CSS
===========

The Org Chart allows to specify custom CSS styles. 
If you are familiar with `CSS <http://www.w3schools.com/css/>`_ , you can adjust visualization of company structure to your brand book.

For example you can change the background of the person’s box to black using such CSS:

.. code:: css

    .poch-web-part .pl-item .pl-item-template{
     background-color: black;
     border-color: black;
     }

And this is another example which resizes Org Chart boxes to smaller size. 
Thus, more boxes can be displayed in the single screen.

.. code:: css

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

On the picture below you can see example of CSS style which changes the background of boxes to black:

.. image:: /../_static/img/advanced-web-part-configuration/custom-css/OrgChart-Configuration-Wizard-11.png
    :alt: Custom css


Printing custom CSS
-------------------

With Org Chart you can also create custom CSS styles that will be applied to the chart only when you print it. 
That way, you can apply custom styles that will help reading the chart after printing it, 
but without affecting the chart on your SharePoint site.

You can change font-size for printing purposes only:

.. image:: /../_static/img/advanced-web-part-configuration/custom-css/ConfWizard_Printing_Font.png
    :alt: Printing

Similarly, you can also change background color of boxes:

.. image:: /../_static/img/advanced-web-part-configuration/custom-css/ConfWizard_Printing_Background.png
    :alt: Printing

Org Chart will add the class "pl-print-mode" to elements before printing out the chart. 
This way, you can handle styles in the “Custom CSS” tab that will be applied only when printing the chart.

To enlarge font-size for printing, the code used was:

.. code:: css

    .pl-print-mode .pl-item-card .field-container {
    font-size: 16px;
    }

And to modify the background color of boxes the following code was added:

.. code:: css

    .pl-print-mode .pl-item .pl-item-template {
    background-color: #e6f4ff !important;
    }


.. Note:: Go to the next step of the advanced configuration wizard `Reset configuration <../configuration-wizard/reset-configuration.html>`_ .
