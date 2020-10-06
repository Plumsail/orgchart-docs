Hide assistant from subordinates
================================

**Update: Org Chart does everything automatically for you since version 2.2.28. It checks if there is already assistant box in the structure and hides subordinate box.**

We have separate fields to store information about manager and assistant in user profiles or SharePoint list data sources. So, it is possible that assistant of specific employee has the same employee as a manager. This brings us to duplicated boxes in the org chart. As you see below, 
Derek Clark is an assistant of David Navarro and at the same time David Navarro is a manager for Derek Clark.


.. image:: /../../_static/img/how-tos/other-examples/hide-assistant-from-subordinates/AssistantDuplicate.png
    :alt: Assistant Duplicate


I will show how to hide assistant from subordinates and display it as assistant only. I will use job title and box context in the configuration wizard to specify appropriate filtration rule.

This is my filtration rule


.. code::

   function(itemData, context){ 
 
     var jobTitleFiled = "Title";
     return context.itemType == "Assistant" || context.itemType == "Item" && !itemData[jobTitleFiled].toLocaleLowerCase().contains("assistant")
 
   }


You can just copy and paste this code to org chart configuration wizard on “Filtration” step if you use user profiles as a data source. 
You may need to specify your own filed internal name for job title field if you use SharePoint list as a data source. 
Just replace **var jobTitleFiled = “Title”** with your field name.

This filtration rule allows to display all assistant boxes and all subordinate boxes except subordinate boxes with job title which contains “assistant” keyword.

As result I have such org chart with single assistant box:


.. image:: /../../_static/img/how-tos/other-examples/hide-assistant-from-subordinates/AssistantSingleBox.png
    :alt: Assistant Single Box
