JavaScript Events
=================

.. contents:: Contents
   :local:
   :depth: 1

ItemData object
---------------

Most rendering events receive :code:`itemData` object as input parameter. The object represents the business object from the data source. It is a set of fields with values. 
Each field has the same name as internal name of the field in the data source.

The object has structure like this:

.. code-block:: javascript

   {
     FieldInternalName1: "FieldValue1",
     FieldInternalName2: "FieldValue2",
     ...
     FieldInternalNameN: "FieldValueN",
   }

.. _onBoxRendered:

onBoxRendered(handler) event
----------------------------

Adds handler on box rendered event. The :code:`handler` function has three input parameters:

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **event**
       -  It is the object of event    
    *  -  **box**
       -  It is the object of rendered box. You can change this box, for example change background.

          The :code:`box` object has following properties:

          - **$elem** – The property stores jQuery object of the box element. You can use all methods available in jQuery to customize the box, for example `css method <http://api.jquery.com/css/>`_.
          - **elem** – The DOM element of the box.
          - **$elemContainer** – The property stores jQuery object of the box container element. 
          You can use this object to set width and height of the box.
          - **elemContainer** – The DOM element of the box container.

          The :code:`box` object also provides :code:`getInnerContent` function. It gets jQuery object for the inner content of current box.
    *  -  **itemData**
       -  It is the business object from the data source. See description at the beginning of "Events" section.

.. rubric:: Example

.. code-block:: javascript

  //Changes background of boxes for all employees
  //from marketing department
  renderer.onBoxRendered(function(event, box, itemData){
    if(itemData["Department"].contains('Marketing')){
      box.$elem.css({
        'background-color': 'red',
        'border-color': 'red'
      });
    }
  });

In this example :code:`Department` is an internal name of the field, you can get value from the business object using such syntax:

.. code-block:: javascript

  itemData.Department  


But if the internal name of your field contains :code:`−` like :code:`SPS–Responsibility` you need to use different syntax:

.. code-block:: javascript

  itemData["SPS-Responsibility"]

The :code:`−` symbol is forbidden in JavaScript, that is why you need to get value of the field using string key.


.. _onTooltipRendered:

onTooltipRendered(handler) event
--------------------------------

Adds handler on tooltip rendered event. The handler has three input parameters:

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **event**
       -  the object of event.    
    *  -  **tooltip**
       -  the object of rendered details tooltip. You can change this tooltip, for example change background.

          The :code:`tooltip` object has following properties:

          - **$elem** – The property stores jQuery object of the box element. You can use all methods available in jQuery to customize the box, for example `css method <http://api.jquery.com/css/>`_.
          - **elem** – The DOM element of the details tooltip.

    *  -  **itemData**
       -  the business object from the data source. See description at the beginning of "Events" section.


.. rubric:: Example

.. code-block:: javascript

  //Changes background for all tooltips of employees
  //from marketing department
  renderer.onTooltipRendered(function(event, tooltip, itemData){
    if(itemData["Department"]contains('Marketing')){
      tooltip.$elem.css({ 'background-color': 'red' });
    }
  });


.. _onSearchResultRendered:

onSearchResultRendered(handler) event
-------------------------------------

Adds handler on quick search result rendered event. The handler has three input parameters:

.. list-table::
    :header-rows: 1
    :widths: 30 70

    *  -  Parameter
       -  Description       
    *  -  **event**
       -  the object of event.    
    *  -  **tooltip**
       -  the object of rendered details tooltip. You can change this tooltip, for example change background.

          The :code:`searchResult` object has following properties:

          - **$elem** – The property stores jQuery object of the box element. You can use all methods available in jQuery to customize the box, for example `css method <http://api.jquery.com/css/>`_.
          - **elem** – The DOM element of the search result.

    *  -  **itemData**
       -  the business object from the data source. See description at the beginning of "Events" section.

.. rubric:: Example

.. code-block:: javascript

  //Changes background for search results of employees
  //from marketing department
  renderer.onSearchResultRendered(
    function(event, searchResult, itemData){
      if(itemData["Department"].contains('Marketing')){
        searchResult.$elem.css({ 'background-color': 'red' });
      }
    }
  );


.. _onInitialLoadingFinished:

onInitialLoadingFinished(handler) event
---------------------------------------

Adds handler on org chart initial loading finished event. It is triggered when org chart is loaded for the first time.

.. rubric:: Example

.. code-block:: javascript

  renderer.onInitialLoadingFinished(
    function(){
      console.log('Initial loading is finished');
    }
  );


.. _onLoadingStarted:

onLoadingStarted(handler) event
-------------------------------

Adds handler on org chart loading started event. It is triggered when progress indicator is showed.

.. rubric:: Example

.. code-block:: javascript

  renderer.onLoadingStarted(
    function(){
      console.log('Loading is started');
    }
  );


.. _onLoadingFinished:

onLoadingFinished(handler) event
--------------------------------


Adds handler on org chart loading finished event. It is triggered when progress indicator is hidden.

.. rubric:: Example

.. code-block:: javascript

  renderer.onLoadingFinished(
    function(){
      console.log('Loading is finished');
    }
  );

.. note:: Next review `Methods <methods.html>`_.