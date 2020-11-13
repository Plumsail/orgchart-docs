Configuration
===================

**Config** stores all configuration settings for Org Chart. You can read it and modify before Org Chart is rendered. 
Thus, you can change configuration based on your logic dynamically.

Just use :code:`renderer.config` outside of any events right in the code editor.

Below are some useful properties from the configuration which you can override. Other properties can be defined in user interface of the configuration wizard, but you can override them also if required.

.. rubric:: Input parameters

.. list-table::
    :header-rows: 1
    :widths: 20 30

    *  -  Property
       -  Description 
    
    *  -  **nodesSortFieldName**
       -  
          Name of field which is used for sorting. For User profiles it is :code:`PreferredName` by default. 
          
          Example:
          
          .. code-block:: javascript
          
            renderer.config.nodesSortFieldName = "PreferredName";
     
    *  -  **nodesSortOrder**
       -  It is :code:`ASC` by default, but you can specify :code:`DESC` for descending sorting.
          
          Example:
          
          .. code-block:: javascript
          
            renderer.config.nodesSortOrder = "DESC";
            
    *  -  **searchResultSortFieldName**
       -  Name of field which is used for sorting. For User profiles you need to use a name of Sortable Managed property. You may find these properties in **SharePoint Central Administration** > **Search** > **Manage Search Schema**.
          
          Example:
          
          .. code-block:: javascript
          
            renderer.config.searchResultSortFieldName = "LastName";
            
    *  -  **searchResultSortOrder**
       -  It is :code:`ASC` by default, but you can specify :code:`DESC` for descending sorting.
          
          Example:
          
          .. code-block:: javascript
          
            renderer.config.searchResultSortOrder = "DESC";
            
    *  -  **searchResultMaxCnt**
       -  Max number of items is search results. It is 10 by default.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.searchResultMaxCnt = 15;
                   
    *  -  **spSearchQueryPattern**
       -  The pattern for a keyword in a search query. You may adjust the severity of the search query with this property. For example, if you specify this property as :code:`{{keyword}}` then the Org Chart will use the search by exact match.It is :code:`{{keyword}}*` by default. :code:`{{keyword}}` is the reserved key and you don’t need to change it. You may get more information about the syntax for the pattern in this `article <https://docs.microsoft.com/en-us/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference>`_ .

          Example:
          
          .. code-block:: javascript
          
            renderer.config.spSearchQueryPattern = "{{keyword}}";
                       
    *  -  **spSearchSourceId**
       -  The GUID of your custom SharePoint Result Source. "Local People Results" result source is using in the Org Chart by default. You may get more information about creating a custom result source by this `link <https://docs.microsoft.com/en-us/sharepoint/search/configure-result-sources-for-search#BKMK_CreateResutlSource>`_ .

          Example:
          
          .. code-block:: javascript
          
            renderer.config.spSearchSourceId = "F2HR7450-98KV-6JA3-23LT-GNZOP20D1S73";
                   
    *  -  **idFieldMapping**
       -  Stores information about field where box id is stored. For example you can extract internal field name like this.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.idFieldMapping.InternalFieldName;
                   
    *  -  **parentIdFieldMapping**
       -  Stores information about field where box parent id is stored. For example you can extract internal field name.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.parentIdFieldMapping.InternalFieldName;
                   
    *  -  **ListDataSourceSettings**
       -  Stores information about list data source. For example you can extract list id.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.ListDataSourceSettings.ListId;
                   
    *  -  **itemsPerNodeLimit**
       -  Limit for items per one node for compact layout. Default value is 100.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.itemsPerNodeLimit = 150;
                   
    *  -  **clientSideCachingLifeDays**
       -  Life time in days for client side cache.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.clientSideCachingLifeDays = 2;
                   
    *  -  **renderInitialNode**
       -  You can disable rendering of initial node if you want to drill down to some other node on web part load. By default it is set to true. It helps to reduce time of initial loading.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.renderInitialNode = false;
                   
    *  -  **RootNodeId**
       -  You can specify root ID dynamically from your code.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.RootNodeId = "account@contoso.onmicrosoft.com";
                   
    *  -  **minSearchKeywordLenght**
       -  Min number of symbols for a search keyword. It is 2 by default.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.minSearchKeywordLenght = 3;
                   
    *  -  **displayDottedLineForSolidEmployee**
       -  Show/hide the feature for displaying dotted-line managers drill down link for boxes. It is true by default.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.displayDottedLineForSolidEmployee = false;
                   
    *  -  **connectionLinesWidth**
       -  Set the width of connections lines between boxes in Org Chart. It is 1 by default.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.connectionLinesWidth = 2;
                   
    *  -  **CsvExportFields**
       -  You can specify a custom array of fields that will be used in the export to CSV. Fields with the item’s current level and the subordinate’s count will be included to the result file automatically.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.CsvExportFields = ["ID", "Title", "Office", "JobTitle"];
               
    *  -  **BoxesCustomization**
       -  Stores the customization for some single boxes. This is the key/value dictionary where the key is an ID of a box and the value is an object of box customization. Available fields for customization: **Orientation** – sets a box’s orientation. Can be :code:`Stacked` or :code:`Horizontal`. It has :code:`Stacked` value by default. **Note**: BoxesCustomization works only for the TopToBottomCompact layout.

          Example:
          
          .. code-block:: javascript
          
            renderer.config.BoxesCustomization = {
              "6": {Orientation: "Horizontal"},
              "3": {Orientation: "Horizontal"}
            };