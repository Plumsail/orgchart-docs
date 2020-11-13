Methods
=========

You can use methods inside events or directly in the JavaScript editor. If you put a method call directly in the editor it is executed when Org Chart web part is loaded. 

.. contents:: Contents
   :local:
   :depth: 1

.. _zoom(value):

zoom(value)
------------

Sets scale for entire Org Chart.

.. rubric:: Input parameters

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **value**
       -  numeric value, for example :code:`0.5`. 

.. rubric:: Example

The example below shows how to set 50% scale for Org Chart:

.. code-block:: javascript

  renderer.zoom(0.5)


.. _drillDown:

drillDown(itemId, completed)
----------------------------

Drills down Org Chart to specified box.

.. rubric:: Input parameters

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **itemId**
       -  Id of item in a data source. For example it is an account name for user profiles or it can be a list item ID for SharePoint list. Mapping for ID field can be configured on the first step of the configuration wizard for SharePoint list data source.
     
    *  -  **completed**
       -  callback function which is executed after drill down.

.. rubric:: Example

The example below shows how to drill down to box of employee with ID equals 3.

.. code-block:: javascript

  renderer.drillDown("3", function(){
    console.log("Drill down executed.");
  });


.. _adjustCenterScroll():

adjustCenterScroll()
--------------------

Displays center of of structure in the middle of the web part.

.. rubric:: Example

The example below shows how to call this method:

.. code-block:: javascript

  renderer.adjustCenterScroll();


.. _render():

render()
---------

Rerenders Org Chart from scratch.

.. rubric:: Example

The example below shows how to call it

.. code-block:: javascript

  renderer.render();


.. _fixConnectionLines():

fixConnectionLines()
--------------------

Sometime if you add content to Org Chart boxes dynamically by JavaScript, connection lines can appear not in correct place. You can use this method to adjust connection lines to newly added content.

.. rubric:: Example

The example below shows how to use this method:

.. code-block:: javascript

  renderer.fixConnectionLines();


.. _initTooltipBasedOnConfig:

initTooltipBasedOnConfig(link, itemData)
----------------------------------------

Initializes tooltips for specified link. If you have custom rendering logic you can use this method to initialize tooltip links. This method will show a tooltip with data from :code:`itemData` when somebody clicks on the link.

.. rubric:: Input parameters

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **link**
       -  jQuery element for the link. Click on the link will show the tooltip.
     
    *  -  **itemData**
       -  The object with properties from a data source. You can receive it from rendering events. Please find the description below at the beginning of the "Events" section.


.. _expandNodeLevels:

expandNodeLevels(numberOfLevels, completed)
-------------------------------------------

Expands specified number of levels of Org Chart.

.. rubric:: Input parameters

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **numberOfLevels**
       -  Number of levels to expand.
     
    *  -  **completed**
       -  callback function which is executed when all levels are expanded.

You can use it together with :code:`showLoadingPanel` and :code:`hideLoadingPanel` functions. Show loading panel before calling this method and hide it inside completed callback.

.. rubric:: Example

.. code-block:: javascript

  renderer.expandNodeLevels(3, function(){
    console.log("Nodes are expanded");
  });


.. _expandNodeLevelsConditionally:

expandNodeLevelsConditionally(maxNumberOfLevels, conditionFunction, completed)
------------------------------------------------------------------------------

Conditionally expands specified number of levels of Org Chart.

.. rubric:: Input parameters

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **maxNumberOfLevels**
       -  Number of levels to expand.
     
    *  -  **conditionFunction**
       -  Function that receives :code:`itemData` object with all box properties. You can use this object in your conditions. The funciton has to return boolean value. If :code:`true` is returned, current box will be expanded.

    *  -  **completed**
       -  callback function which is executed when all levels are expanded.


You can use it together with :code:`showLoadingPanel` and :code:`hideLoadingPanel` functions. Show loading panel before calling this method and hide it inside completed callback.

.. rubric:: Example

The example below shows how to use this function together with :code:`onInitialLoadingFinished` event and :code:`showLoadingPanel` method. It waits untill the web part is loaded in :code:`onInitialLoadingFinished` event. Then it shows loading panel by calling :code:`showLoadingPanel`. Then it validates condition for each box in :code:`conditionFunction`. Once all levels are expanded, it hides loading panel by calling :code:`hideLoadingPanel` method.


.. code-block:: javascript

  renderer.onInitialLoadingFinished(function () {

    //Show loading panel before expanding
    renderer.showLoadingPanel();

  renderer.expandNodeLevelsConditionally(2, 
    function (itemData) {

      //Expand all employees except "Derek Clark"
      return itemData["PreferredName"] != "Derek Clark";

    }, function () {

      //Hide loading panel after expanding
      renderer.hideLoadingPanel();
    });
  });


.. _collapseAllNodes:

collapseAllNodes(completed)
---------------------------

Collapse all levels of Org Chart.

.. rubric:: Input parameters

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **completed**
       -  callback function which is executed when all levels are expanded.


You can show loading panel before calling this method and hide it inside completed callback with :code:`showLoadingPanel` and :code:`hideLoadingPanel` functions.

.. rubric:: Example

The example below shows how to use this function together with :code:`onInitialLoadingFinished` event and :code:`showLoadingPanel` method. It waits untill the web part is loaded in :code:`onInitialLoadingFinished` event. Once all levels are collapsed, it hides loading panel by calling :code:`hideLoadingPanel` method.

.. code-block:: javascript

  renderer.onInitialLoadingFinished(function () {

    //Show loading panel before collapsing
    renderer.showLoadingPanel();

    renderer.collapseAllNodes(function () {

      //Hide loading panel after expanding
      renderer.hideLoadingPanel();

    });
  });


.. _prerenderAction:

prerenderAction(completed)
---------------------------

You can use this method to preform some actions before Org Chart rendering. For example if you need to load some data or some scripts you can hold Org Chart loading and continue it once everything is ready.

.. rubric:: Input parameters

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **completed**
       -  callback function which is executed when all levels are expanded.


Be careful with this method because if you don’t call :code:`completed` function, Org Chart is never rendered. We recommend you to wrap your code with :code:`try – catch – finally` to guarantee that :code:`completed` function is called.

.. rubric:: Example

.. code-block:: javascript

  renderer.prerenderAction = function(completed){
    try {
      //Do some initialization staff  }
    catch(err) {
      //handle errors  } 
    finally {
      //Org chart will not start rendering
      //until you call 'completed' function
      completed();
    }
  }


.. _showLoadingPanel:

showLoadingPanel()
------------------

It shows loading screen for the Org Chart web part.

.. rubric:: Example

.. code-block:: javascript

  renderer.showLoadingPanel();

.. _hideLoadingPanel:

hideLoadingPanel()
--------------------

It hides loading screen for the Org Chart web part.

.. rubric:: Example

.. code-block:: javascript

  renderer.hideLoadingPanel();


.. _enableDisableFullScreen:

enableDisableFullScreen()
-------------------------

It toggles full screen mode for the Org Chart web part.

.. rubric:: Example

In the example below I check if there is the URL parameter :code:`IsFullScreen` and show Org Chart enable full scheen if it is there.

.. code-block:: javascript

  var isFullScreen = GetUrlKeyValue("IsFullScreen");
                      
  if(isFullScreen === "true"){
    renderer.enableDisableFullScreen();
  }


.. _dataProvider.getBoxGroupItemDataById:

dataProvider.getBoxGroupItemDataById(id, completed, error)
----------------------------------------------------------

Get org chart data item by id (usually account name or list id). 

.. rubric:: Example

.. code-block:: javascript

  renderer.dataProvider.getBoxGroupItemDataById("3", function(dataItem){
    console.log(dataItem)
  });


.. _dataProvider.getCurrentUserAccountName:

dataProvider.getCurrentUserAccountName(completed, error)
----------------------------------------------------------

Get account name of a current logged in user. 

.. rubric:: Example

.. code-block:: javascript

  renderer.dataProvider.getCurrentUserAccountName(function(accountName){
    console.log(accountName);
  });


.. _dataProvider.clearCache:

dataProvider.clearCache()
--------------------------

Clears client side cache for current browser. 

.. rubric:: Example

.. code-block:: javascript

  renderer.dataProvider.clearCache();


.. _scrollToBox:

scrollToBox(id)
----------------

Scroll org chart to item by id (usually account name or list id). 

.. rubric:: Example

.. code-block:: javascript

  renderer.scrollToBox("domain\\username");

.. _customFunctions.getNumberOfColumns:

customFunctions.getNumberOfColumns(rootItemData, defaultColumnsNumber)
-----------------------------------------------------------------------

You may use this method to perform some custom logic for setting the number of columns for the root item in the compact layout dynamically. For example, if you need to change the default value from the **Layout** step of the configuration wizard for one of the users. 

**Note:** This method must return a number value. The default value will be taken otherwise.

.. rubric:: Input parameters

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **rootItemData**
       -  The business object from the data source. See description at the beginning of "Events" section.     
    *  -  **defaultColumnsNumber**
       -  The default value from the configuration wizard.


.. rubric:: Example

.. code-block:: JavaScript

  renderer.customFunctions.getNumberOfColumns = 
    function(rootItemData, defaultColumnsNumber){
    if(rootItemData["Title"] === "David Navarro"){
      return 2;
    }
    return defaultColumnsNumber;
  }

.. note:: Next review `Configuration <configuration.html>`_.