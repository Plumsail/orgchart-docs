How to create an org chart with two root managers in SharePoint Online, SharePoint 2019 / 2016 / 2013 and Microsoft 365
========================================================================================================================


In this article, I will describe how to create org chart with two root managers. This approach is supported by `Plumsail Org Chart <https://plumsail.com/sharepoint-orgchart/>`_ for SharePoint 2013, SharePoint 2016, SharePoint 2019 or for SharePoint Online in Office 365.

You may use the following trick if you need to build a chart with two or more root nodes, for example, if you have multiple CEOs at the top of the hierarchy.


.. image:: /../_static/img/how-tos/customize-boxes-and-styles/create-an-orgchart-with-two-root-managers/two-root-nodes.png
    :alt: Two root nodes


To do that you need to add a fake manager at the top of your chart and then hide it using Custom JavaScript and CSS:


.. image:: /../_static/img/how-tos/customize-boxes-and-styles/create-an-orgchart-with-two-root-managers/fake-managet-at-the-top.png
    :alt: Fake manager on the top


Add the following script to the Custom JavaScipt tab to hide the fake manager:

.. code-block:: javascript

  renderer.onBoxRendered(function(event, box, itemData){
    if (itemData["Title"].contains("David Navarro")) {
      box.$elem.hide();
      $("div.poch-group").addClass("hiddenElements");
      $("div.poch-node").prepend('<div class="maskingBlock"></div>');
    }
  });


.. image:: /../_static/img/how-tos/customize-boxes-and-styles/create-an-orgchart-with-two-root-managers/fake-manager-hide.png
    :alt: Hide fake manager


Then, add the following styles to the Custom CSS tab for covering the lines left from the hidden box. The styles differ depending on the layout you use. Also, you may need to change the background color or other properties for adjusting the masking block to a selected skin.

.. image:: /../_static/img/how-tos/customize-boxes-and-styles/create-an-orgchart-with-two-root-managers/two-root-nodes-lines.png
    :alt: Two root nodes


.. rubric:: Top to bottom (any)

.. code-block:: css

  .hiddenElements {
    overflow: hidden;
    margin: 0 !important
  }

  .maskingBlock {
    display: block;
    width: 100%;
    height: 50px;
    background-color: white;
    position: absolute;
    left: 0;
    top: 0
  }


.. rubric:: Left to right

.. code-block:: css

  .hiddenElements {
    overflow: hidden;
    margin: 0 !important
  }		
 
  .maskingBlock {
    display: block;
    width: 100%;
    height: 70px;
    background-color: white;
    position: absolute;
    left: 0;
    top: 0
  }


.. rubric:: Bottom to top

.. code-block:: css

  .hiddenElements {
    overflow: hidden;
    margin: 0 !important
  }
 
  .maskingBlock {
    display: block;
    width: 100%;
    height: 60px;
    background-color: white;
    position: absolute;
    left: 0;
    bottom: 0;
    z-index: 20
  }


That is it. Now you have a chart with multiple managers at the top:

.. image:: /../_static/img/how-tos/customize-boxes-and-styles/create-an-orgchart-with-two-root-managers/two-root-nodes-lines.png
    :alt: Two root nodes


Conclusion
----------

Now you know how to use `Plumsail Org Chart <https://plumsail.com/sharepoint-orgchart/>`_ to create org chart with two root managers. 
If you didn’t install it yet, `download <https://plumsail.com/sharepoint-orgchart/download/>`_ it 
and follow the installation instruction for your version of SharePoint in the `documentation <../getting-started/quick-configuration.html>`_ . 
It is quite easy to get started.