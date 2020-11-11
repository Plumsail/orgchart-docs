Display awards and conditionally format SharePoint Org Chart
============================================================

In this article I will show how to conditionally format Org Chart boxes and search results according to field values from data source, for example User Profile Service or SharePoint list. 
`SharePoint OrgChart <https://plumsail.com/sharepoint-orgchart/>`_ 1.7.1 and higher allows to add dynamics to boxes using JavaScript. Usually we need to highlight boxes according to some quite simple rule, but sometimes we need to implement more difficult logic. In this article, I will show how to simply highlight boxes with specific color as well as show more complex case with displaying awards and search result highlighting. As a result, I want to change background of boxes and search results according to field values from data source and add gold, silver or bronze medals to boxes of the best employees.

I divided this article into three main steps:

1. :ref:`highlight-boxes-according-to-field-value-from-data-source`.
2. :ref:`add-images-awards-or-any-other-html-into-boxes-dynamically-using-javascript`.
3. :ref:`complete-guide-with-ready-to-copy-paste-code-for-both-steps-above`.

In the first step, I will show how to implement color codding for org chart. If you don’t need any additional functionality, you can read the first step only. If you need to implement more complex case and modify boxes dynamically, for example add images to boxes, please read the second and the third steps.

This is how the org chart will look after all customizations:

.. image:: /../_static/img/how-tos/customize-boxes-and-styles/display-awards-and-conditionally-format-orgchart/OrgChartWithAwards.png
    :alt: OrgChart Awards


.. _highlight-boxes-according-to-field-value-from-data-source:

Highlight boxes according to field values
-----------------------------------------

I assume that you’ve already added the web part to your page and configured it with default settings.

I want to change background of boxes according to custom field from the data source. In my case it is ‘Awards’ field, which has following possible values:

- Gold medal
- Silver medal
- Bronze model

I want to set light goldenrod background for boxes, where ‘Awards’ field has value ‘Gold medal’, to set lavender background for boxes with ‘Silver medal’ field value and to set maize background for boxes with ‘Bronze medal’ field value.

First of all I added ‘Awards’ field to my data source. I used SharePoint list as a data source, but you can use User Profile Service as well. If you don’t know how to add new field to your data source, read official Microsoft documentation:

- `Add new field to SharePoint list <http://office.microsoft.com/en-001/sharepoint-server-help/create-change-or-delete-a-column-in-a-list-or-library-HA102771913.aspx>`_
- `Add new property to User Profile Service <http://office.microsoft.com/en-001/office365-sharepoint-online-enterprise-help/add-and-edit-user-profile-properties-HA102772741.aspx>`_


Then I configured the web part using the configuration wizard. Let me show how.

I opened page with Org Chart web part for edit:

.. image:: /../_static/img/how-tos/customize-boxes-and-styles/display-awards-and-conditionally-format-orgchart/EditPage.png
    :alt: Edit page


Then I opened Org Chart web part properties, by clicking in right top corner of web part and selecting Edit Web Part:

.. image:: /../_static/img/how-tos/customize-boxes-and-styles/display-awards-and-conditionally-format-orgchart/editwebpart.png
    :alt: Edit page


Then I switched to the ‘General settings’ wizard step and changed org chart skin to ‘Modern’. I would prefer to use this skin because it fits modern UI of SharePoint Online more than other skins.

Then I switched to the ‘Custom JavaScript’ wizard step:

.. image:: /../_static/img/how-tos/customize-boxes-and-styles/display-awards-and-conditionally-format-orgchart/CustomJSStep.png
    :alt: Custom javascript

As you can see on the picture above, there is ready to use JavaScript handler with three functions, which allow to subscribe for box, tooltip or search result rendering event. In this article I used only box and search result rendering events to highlight boxes and search results with color. 
You can find description of JavaScript framework in `the documentation <../javascript-framework/introduction.html>`_.

It is possible to use such code to highlight boxes with ‘Gold medal’ field values:

..code::

   //subscribe for box rendering event
   renderer.onBoxRendered(function(event, box, itemData){  
   //If employee has gold award show medal and add CSS classes
   if(itemData.Awards == 'Gold medal'){
     box.$elem.css({
       'background-color': '#ffec8b' /*light goldenrod*/
     });
   }  
  });


As you can see from the script above I used **onBoxRendered** method to subscribe for event. 
The method receives box and **itemData** parameters. I used **‘Awards’** property of the **‘itemData’** parameter to check if current employee has award. 
The **itemData** parameter contains all field values from the data source mentioned in the configuration wizard. 
Then I applied CSS style using jQuery css function to **‘$elem’** property of the box. The **box** parameter represents object of current box and **$elem** property stores jQuery object for the box element. 
That is all required to modify color of the box according to the property of employee:

.. image:: /../_static/img/how-tos/customize-boxes-and-styles/display-awards-and-conditionally-format-orgchart/GoldBox.png
    :alt: Gold box


To highlight boxes with other field values you can use the same logic and add if condition for each of them. 
Such approach also works for search results and tooltips. So, if you need to add simple CSS styles you can do it right in the JavaScript, 
but to keep code readable I would recommend to move CSS outside from JavaScript code.

That is why I created CSS class for box. You can see the CSS style for gold medal box below:

.. code:: css

   /*set background color for box with gold medal*/
   .pl-item-template.gold-box {
     background-color: #ffec8b !important;
   }

To apply CSS style I switched to ‘General settings’ and copied style to ‘Custom CSS’ property. Then switched back to JavaScript and changed it to following:

.. code:: javascript

    renderer.onBoxRendered(function(event, box, itemData){  
    //If employee has gold award show medal and add CSS classes
     if(itemData.Awards == 'Gold medal'){                
     box.$elem.addClass('gold-box');            
     }
    });

As you see, I just added CSS class to **$elem** instead of adding CSS styles manually.

In this step I showed part of script for my case only. I don’t want to overload this step by code, you can find complete script and CSS styles in the last step of the article.


.. _add-images-awards-or-any-other-html-into-boxes-dynamically-using-javascript:

Add images (awards) or any other HTML into boxes dynamically
------------------------------------------------------------

In this step I will show how to use JavaScript to modify org chart boxes dynamically. I will add image of award into the box. To keep explanation clear I will not use script from the previous step here, but you can find combined script in the next step.

You can see the JavaScript code I used below:

.. code:: javascript

    renderer.onBoxRendered(function(event, box, itemData){  
    //If employee has gold award show medal and add CSS classes
    if(itemData.Awards == 'Gold medal'){
      var medalSpan = $('<span class="medal gold-medal"></span>');    
      box.getInnerContent().append(medalSpan);  
    }  
    });

The code above checks if current item has ‘Gold medal’ and adds a span element into box. 
I used ‘getInnerContent’ function of the box parameter to get jQuery object for the inner content of current box. 
I added ‘medal’ and ‘gold-medal’ CSS classes to the span. 
I used ‘medal’ class to configure position and size for all medals and ‘gold-medal’ class to set background image for gold medal. 
You can see CSS style below:

.. code:: css

   /*set position for all medals*/
   .medal {
     display: block;  
     position: absolute;
     width: 32px;
     height: 32px;
     top: 60px;
     left: 0px;
   }
 
   /*set image URL for gold medal*/
   .gold-medal {
   background-image: url(../SiteAssets/OrgChart/gold-medal32x32.png);
   }

.. note:: I uploaded images for medals to OrgChart folder of SiteAssets document library, but you can use any other location. Do not forget to update the path to image in the CSS style according to your location.


It is enough to add medal to Org Chart box:

.. image:: /../_static/img/how-tos/customize-boxes-and-styles/display-awards-and-conditionally-format-orgchart/BoxWithGoldMedal.png
    :alt: Box with gold medal

In this step I showed how to add HTML elements to boxes dynamically. In my case it was image of the gold medal. I showed part of script and CSS styles for gold medal only, but you can find complete script in the next step.


.. _complete-guide-with-ready-to-copy-paste-code-for-both-steps-above:


Step by step guide with ready to copy paste code
------------------------------------------------

Add new ‘Awards’ field to your data source, SharePoint list or User Profile Service. If you don’t know how to do it, read official documentation from Microsoft:

- `Add new field to SharePoint list <http://office.microsoft.com/en-001/sharepoint-server-help/create-change-or-delete-a-column-in-a-list-or-library-HA102771913.aspx>`_
- `Add new property to User Profile Service <http://office.microsoft.com/en-001/office365-sharepoint-online-enterprise-help/add-and-edit-user-profile-properties-HA102772741.aspx>`_


Open the configuration wizard using the context menu in the top right corner of the web part.

Switch to ‘General settings’ wizard step and choose ‘Light gray’ skin.

Copy CSS style and paste it to ‘Custom CSS’ property:

.. code:: css

   /*set position for all medals*/
   .medal {
     display: block;
     width: 32px;
     height: 32px;
     position: absolute;
     top: 60px;
     left: 0px;
   }
 
   /*set image URL for gold medal*/
   .gold-medal {
     background-image: url(../SiteAssets/OrgChart/gold-medal32x32.png);
   }
 
   /*set image URL for silver medal*/
   .silver-medal {
     background-image: url(../SiteAssets/OrgChart/silver-medal32x32.png);
   }
 
   /*set image URL for bronze medal*/
   .bronze-medal {
   background-image: url(../SiteAssets/OrgChart/bronze-medal32x32.png);
   }
 
   /*set background color for box with gold medal*/
   .pl-item-template.gold-box, .gold-search-result{
   background-color: #ffec8b !important;
   }
 
   /*set background color for box with silver medal*/
   .pl-item-template.silver-box, .silver-search-result{
   background-color: #e6e6fa !important;
   }
 
   /*set background color for box with bronze medal*/
   .pl-item-template.bronze-box, .bronze-search-result{ 
     background-color: #edd19c !important;  
   }


Switch to ‘Custom JavaScript’ wizard step and add ‘Awards’ field to fields included to org chart data object.

Then copy JavaScript code and paste it to the code editor:


.. code:: javascript

   //subscribe for box rendering event
   renderer.onBoxRendered(function(event, box, itemData){
  
   //If employee has gold award show medal and add CSS classes
   if(itemData.Awards == 'Gold medal'){
     var medalSpan = $('<span class="medal gold-medal"></span>');         
     box.getInnerContent().append(medalSpan);
     box.$elem.addClass('gold-box');            
   }
  
   //If employee has silver award show medal and add CSS classes
   if(itemData.Awards == 'Silver medal'){    
     var medalSpan = $('<span class="medal gold-medal"></span>');      
     box.getInnerContent().append(medalSpan);
     box.$elem.addClass('silver-box'); 
   }
  
   //If employee has bronze award show medal and add CSS classes
   if(itemData.Awards == 'Bronze medal'){        
      var medalSpan = $('<span class="medal gold-medal"></span>');  
      box.getInnerContent().append(medalSpan);
      box.$elem.addClass('bronze-box'); 
    }
   });
 
   //subscribe for search result rendering event
   renderer.onSearchResultRendered(function(event, searchResult, itemData){  
  
   //add class to search result of employee with gold medal
   if(itemData.Awards == 'Gold medal'){    
    searchResult.$elem.addClass('gold-search-result');            
   }
    
   //add class to search result of employee with silver medal  
   if(itemData.Awards == 'Silver medal'){        
     searchResult.$elem.addClass('silver-search-result'); 
   }
    
   //add class to search result of employee with bronze medal
   if(itemData.Awards == 'Bronze medal'){            
     searchResult.$elem.addClass('bronze-search-result'); 
   }
  });

Finish the configuration wizard and you will see the org chart with conditional formatting and awards like on the picture in the beginning of this article.


.. image:: /../_static/img/how-tos/customize-boxes-and-styles/display-awards-and-conditionally-format-orgchart/GoldBoxWithMedal.png
    :alt: Gold box with medal


Conclusion
----------

In this article I showed how to add conditional formatting to SharePoint org chart. Now you know how to change background of boxes according to field values from data source in six lines of code. The same logic is applicable to tooltips and search results of org chart. If you need to implement more complex scenario, you can add HTML elements to boxes dynamically using jQuery framework.

I hope this will help you to build clear and useful organization structure.