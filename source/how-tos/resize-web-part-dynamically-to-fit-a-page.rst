Resize web part dynamically to fit a page
=========================================

In this quick tip I will show how to resize SharePoint Org Chart dynamically to fit page content. 
So, when you resize your browser window, Org Chart occupies whole page content. It will look like this:


.. image:: /../_static/img/how-tos/manage-web-part-size-and-scale/resize-web-part-dynamically-to-fit-a-page/OrgChartFitPage.png
    :alt: OrgChart fit page


.. note:: this works for out of the box master page ‘Seatle’ or for masterpages created based on ‘Seatle’.


Just open the Org Chart configuration wizard using ‘gears’ icon at the top right corner of the web part. 
Then paste following JavaScript code to ‘Custom JavaScript’ step:

.. code:: JavaScript

   function isEditMode(){
    try {
    var inDesignMode = document.forms[MSOWebPartPageFormName].MSOLayout_InDesignMode.value;
 
    if (inDesignMode) {
       return true;
    }
 
    var wikiInEditMode = document.forms[MSOWebPartPageFormName]._wikiPageMode ? document.forms[MSOWebPartPageFormName]._wikiPageMode.value : "";
 
    if (wikiInEditMode == "Edit") {
      return true;
    }
 
    return false;
    }
    catch (e) { 
    return false;
    }
   }

 
   if(!isEditMode()){
 
    var wp = $(".poch-web-part").closest("[webpartid]") 
    wp.addClass("pochWebPart");
    wp.height("auto");
 
    var titleRowHeight = $("#s4-titlerow").outerHeight(true);
    $("#contentRow").css({top: titleRowHeight}); 
 
   }


Then switch to ‘Custom CSS’ step and paste following CSS styles into the editor:


.. code:: css

   .pochWebPart{
    position: absolute!important;
    left: 0px;
    right: 0px;
    bottom: 20px;
    top: 0px;
   }
 
   #contentBox{
   position: absolute;
   top: 0px;
   left: 0px;
   right: 0px;
   bottom: 0px;
   }
 
   #s4-bodyContainer{
   position: absolute;
   top: 0px;
   left: 0px;
   bottom: 0px;
   right: 0px;
   }
 
   #contentRow{
   position: absolute;
   top: 91px;
   left: 0px;
   bottom: 0px;
   right: 0px;
   }


That is all. Finish the wizard.