Open Org Chart in full-screen mode on load
==========================================

In this tip, I will describe how to open Org Chart in full-screen mode on load.


You just need to open the configuration wizard (click on gears at the top right corner of the web part and choose “Settings”) and  switch to “Custom JavaScript” step:


.. image:: /../../_static/img/how-tos/manage-web-part-size-and-scale/open-orgchart-in-full-screen-mode-on-load/ConfigWizard2.png
    :alt: Settings


Add the code below into code editor: 

.. code:: JavaScript

   renderer.onInitialLoadingFinished(function(event){
      renderer.enableDisableFullScreen(); 
   });


.. image:: /../../_static/img/how-tos/manage-web-part-size-and-scale/open-orgchart-in-full-screen-mode-on-load/ConfigWizardFullSizeMode.png
    :alt: Configuration full size mode


Then finish the wizard. This script will enable a full-screen mode for your OrgChart when it loads.