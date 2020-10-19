Events
=======

Most rendering events receive **itemData** object as input parameter. The object represents the business object from the data source. It is a set of fields with values. 
Each field has the same name as internal name of the field in the data source.

The object has structure like this:

.. code:: javascript

   {
     FieldInternalName1: "FieldValue1",
     FieldInternalName2: "FieldValue2",
     ...
     FieldInternalNameN: "FieldValueN",
   }



List of events
---------------

- :ref:`onBoxRendered`
- :ref:`onTooltipRendered`
- :ref:`onSearchResultRendered`
- :ref:`onInitialLoadingFinished`
- :ref:`onLoadingStarted`
- :ref:`onLoadingFinished`


.. _onBoxRendered:

onBoxRendered(handler)
----------------------

Adds handler on box rendered event. The handler has three input parameters:

- **event** – the object of event.
- **box** – the object of rendered box. You can change this box, for example change background.
- **itemData** – the business object from the data source. See description at the beginning of ‘Events’ section.

The ‘box’ object has following properties:

- **$elem** – The property stores jQuery object of the box element. 
You can use all methods available in jQuery to customize the box, for example `css method <http://api.jquery.com/css/>`_ .

- **elem** – The DOM element of the box.

- **$elemContainer** – The property stores jQuery object of the box container element. 
You can use this object to set width and height of the box.

- **elemContainer** – The DOM element of the box container.

The ‘box’ object also provides “getInnerContent” function. It gets jQuery object for the inner content of current box.

Example:

.. code:: javascript

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


.. note:: In this example ‘Department’ is an internal name of the field, you can get value from the business object using such syntax:

..code:: javascript

   itemData.Department


But if the internal name of your field contains ‘−‘ like ‘SPS–Responsibility’ you need to use different syntax:

.. code:: javascript

   itemData["SPS-Responsibility"]



The ‘−‘ symbol is forbidden in JavaScript, that is why you need to get value of the field using string key.


.. _onTooltipRendered:

onTooltipRendered(handler)
--------------------------

Adds handler on tooltip rendered event. The handler has three input parameters:

- **event** – the object of event.
- **tooltip** – the object of rendered details tooltip. You can change this tooltip, for example change background.
- **itemData** – the business object from the data source. See description at the beginning of ‘Events’ section.


The ‘tooltip’ object has following properties:

- **$elem** – The property stores jQuery object of the box element. 
You can use all methods available in jQuery to customize the box, for example `css method <http://api.jquery.com/css/>`_ .

- **elem** – The DOM element of the box.


Example:

.. code:: javascript

   //Changes background for all tooltips of employees
   //from marketing department
   renderer.onTooltipRendered(function(event, tooltip, itemData){
     if(itemData["Department"]contains('Marketing')){
         tooltip.$elem.css({ 'background-color': 'red' });
     }
   });


.. _onSearchResultRendered:

onSearchResultRendered(handler)
-------------------------------

Adds handler on quick search result rendered event. The handler has three input parameters:

- **event** – the object of event.
- **searchResult** – the object of rendered search result. You can change this search result, for example change background.
- **itemData** – the business object from the data source. See description at the beginning of ‘Events’ section.


The ‘searchResult’ object has following properties::

- **$elem** – The property stores jQuery object of the box element. 
You can use all methods available in jQuery to customize the box, for example `css method <http://api.jquery.com/css/>`_ .

- **elem** – The DOM element of the box.

Example:

.. code:: javascript

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

onInitialLoadingFinished(handler)
---------------------------------

Adds handler on org chart initial loading finished event. It is triggered when org chart is loaded for the first time.

Example: 

.. code:: javascript

   renderer.onInitialLoadingFinished(
     function(){
         console.log('Initial loading is finished');
     }
   );


.. _onLoadingStarted:

onLoadingStarted(handler)
-------------------------

Adds handler on org chart loading started event. It is triggered when progress indicator is showed.

Example: 

.. code:: javascript

   renderer.onLoadingStarted(
     function(){
         console.log('Loading is started');
     }
   );


.. _onLoadingFinished:

onLoadingFinished(handler)
-------------------------


Adds handler on org chart loading finished event. It is triggered when progress indicator is hidden.

Example: 

.. code:: javascript

   renderer.onLoadingFinished(
     function(){
         console.log('Loading is finished');
     }
   );