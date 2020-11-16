Custom styles for printed Org Chart in SharePoint and Microsoft Teams
=====================================================================

With `Plumsail Org Chart <https://plumsail.com/sharepoint-orgchart/>`_ you can also create custom CSS styles that will be applied to the chart only when you print it. 
That way, you can apply custom styles that will help reading the chart after printing it, 
but without affecting the chart on your SharePoint site.

You can change font-size for printing purposes only:

.. image:: /../_static/img/advanced-web-part-configuration/custom-css/ConfWizard_Printing_Font.png
    :alt: Printing

Similarly, you can also change background color of boxes:

.. image:: /../_static/img/advanced-web-part-configuration/custom-css/ConfWizard_Printing_Background.png
    :alt: Printing

You need to open the configuration wizard and switch to the `Custom CSS step <../configuration-wizard/custom-css.html>`_. Then paste the CSS styles described below into the editor. 

Org Chart will add the class :code:`pl-print-mode` to elements before printing out the chart. 
This way, you can handle styles in the **Custom CSS** tab that will be applied only when printing the chart.

To enlarge font-size for printing, the code used was:

.. code-block:: css

  .pl-print-mode .pl-item-card .field-container {
    font-size: 16px;
  }

And to modify the background color of boxes the following code was added:

.. code-block:: css

  .pl-print-mode .pl-item .pl-item-template {
    background-color: #e6f4ff !important;
  }