Structure of the context object
===============================

Handlebars template receives context object, the object which represents data to render. This context object is used to resolve values in the template. The context object is a plain object with multiple fields from a data source:

.. code:: javascript

   {
     FieldInternalName1: "FieldValue1",
     FieldInternalName2: "FieldValue2",
     ...
     FieldInternalNameN: "FieldValueN",
   }


Thus, you can access the value of the field with internal name ‘FieldInternalName1’ using such Handlebars expression:

.. code::

   {{FieldInternalName1}}