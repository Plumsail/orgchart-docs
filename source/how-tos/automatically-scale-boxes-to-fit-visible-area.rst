How to automatically scale boxes to fit visible area for Org Chart in SharePoint and Microsoft Teams
====================================================================================================


.. note:: This post is actual for Org Chart since version 2.2.24


In this tip I will describe how to automatically resize boxes to fit visible area of the web part. If you have many employees in your org chart it could look like this:


.. image:: /../_static/img/how-tos/manage-web-part-size-and-scale/automatically-scale-boxes-to-fit-visible-area/BoxesAreOutside.jpg
    :alt: Boxes are outside


As you can see some of the boxes are outside of visible area. I will show how to automatically scale boxes to fit web part:


.. image:: /../_static/img/how-tos/manage-web-part-size-and-scale/automatically-scale-boxes-to-fit-visible-area/BoxesFitWebPart.jpg
    :alt: Boxes fit web part


Just open the configuration wizard by clicking gears at the top right corner of the web part. Then click **Settings**. Switch to **Custom JavaScript** step and put the code below into code editor:


.. code-block:: javascript

  renderer.onInitialLoadingFinished(function () {

    renderer.showLoadingPanel();

    var $pochContent = renderer.querySelector(".poch-content")
    var $viewPort = renderer.querySelector(".poch-control").children().first();
    var viewPort = $viewPort[0];
    var topOffset = 20;
    var currentZoom = 1;

    function adjustWidth() {

      var realViewPortWidth = viewPort.scrollWidth * currentZoom;
      var contentWidth = $pochContent.width();

      if (realViewPortWidth > contentWidth) {

        currentZoom = currentZoom - 0.1;
        if (currentZoom > 0) {
          renderer.zoom(currentZoom);
          adjustWidth();
        }
      } else {
        renderer.hideLoadingPanel();
        renderer.dataProvider.getRootItemId(function (rootId) {
          renderer.scrollToBox(rootId);
        });
      }
    }

    setTimeout(adjustWidth, 50);

  });


Then finish the wizard. 
This script calculates visible area, and resizes org chart until it fits width of visible area.