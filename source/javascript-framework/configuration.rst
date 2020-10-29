Configuration
===================

**Config** stores all configuration settings for Org Chart. You can read it and modify before Org Chart is rendered. 
Thus, you can change configuration based on your logic dynamically.

Just use **renderer.config** outside of any events right in the code editor.

Some useful properties from the configuration which you can override:

.. rubric:: Input parameters

.. list-table::
    :header-rows: 1
    :widths: 60 30 30

    *  -  Property
       -  Description
       -  Example       
    *  -  **nodesSortFieldName**
       -  Name of field which is used for sorting. For User profiles it is “PreferredName” by default.
       -  :code:`renderer.config.nodesSortFieldName = "PreferredName";`
     
    *  -  **nodesSortOrder**
       -  It is “ASC” by default, but you can specify “DESC” for descending sorting.
       -  :code:`renderer.config.nodesSortOrder = "DESC";`
            
    *  -  **searchResultSortFieldName**
       -  Name of field which is used for sorting. For User profiles you need to use a name of Sortable Managed property. You may find these properties in SharePoint Central Administration -> Search -> Manage Search Schema.
       -  :code:`renderer.config.searchResultSortFieldName = "LastName";`
            
    *  -  **searchResultSortOrder**
       -  It is “ASC” by default, but you can specify “DESC” for descending sorting.
       -  :code:`renderer.config.searchResultSortOrder = "DESC";`
            
    *  -  **searchResultMaxCnt**
       -  Max number of items is search results. It is 10 by default.
       -  :code:`renderer.config.searchResultMaxCnt = 15;`
                   
    *  -  **spSearchQueryPattern**
       -  The pattern for a keyword in a search query. You may adjust the severity of the search query with this property. For example, if you specify this property as “{{keyword}}” then the Org Chart will use the search by exact match.It is “{{keyword}}*” by default. {{keyword}} is the reserved key and you don’t need to change it. You may get more information about the syntax for the pattern in this `article <https://docs.microsoft.com/en-us/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference>`_ .
       -  :code:`renderer.config.spSearchQueryPattern = "{{keyword}}";`
                       
    *  -  **spSearchSourceId**
       -  the GUID of your custom SharePoint Result Source. “Local People Results” result source is using in the Org Chart by default. You may get more information about creating a custom result source by this `link <https://docs.microsoft.com/en-us/sharepoint/search/configure-result-sources-for-search#BKMK_CreateResutlSource>`_ .
       -  :code:`renderer.config.spSearchSourceId = "F2HR7450-98KV-6JA3-23LT-GNZOP20D1S73";`
                   
    *  -  **idFieldMapping**
       -  Stores information about field where box id is stored. For example you can extract internal field name like this.
       -  :code:`renderer.config.idFieldMapping.InternalFieldName;`
                   
    *  -  **parentIdFieldMapping**
       -  stores information about field where box parent id is stored. For example you can extract internal field name.
       -  :code:`renderer.config.parentIdFieldMapping.InternalFieldName;`
                   
    *  -  **ListDataSourceSettings**
       -  stores information about list data source. For example you can extract list id.
       -  :code:`renderer.config.ListDataSourceSettings.ListId;` 
                   
    *  -  **itemsPerNodeLimit**
       -  limit for items per one node for compact layout. Default value is 100.
       -  :code:`renderer.config.itemsPerNodeLimit = 150;` 
                   
    *  -  **clientSideCachingLifeDays**
       -  life time in days for client side cache.
       -  :code:`renderer.config.clientSideCachingLifeDays = 0.5;` 
                   
    *  -  **renderInitialNode**
       -  you can disable rendering of initial node if you want to drill down to some other node on web part load. By default it is set to true. It helps to reduce time of initial loading.
       -  :code:`renderer.config.renderInitialNode = false;`
                   
    *  -  **RootNodeId**
       -  you can specify root ID dynamically from your code.
       -  :code:`renderer.config.RootNodeId = "account@contoso.onmicrosoft.com"` 
                   
    *  -  **minSearchKeywordLenght**
       -  min number of symbols for a search keyword. It is 2 by default.
       -  :code:`renderer.config.minSearchKeywordLenght = 3` 
                   
    *  -  **displayDottedLineForSolidEmployee**
       -  show/hide the feature for displaying dotted-line managers drill down link for boxes. It is true by default.
       -  :code:`renderer.config.displayDottedLineForSolidEmployee = false`     
                   
    *  -  **connectionLinesWidth**
       -  set the width of connections lines between boxes in Org Chart. It is 1 by default.
       -  :code:`renderer.config.connectionLinesWidth = 2` 
                   
    *  -  **CsvExportFields**
       -  you can specify a custom array of fields that will be used in the export to CSV. Fields with the item’s current level and the subordinate’s count will be included to the result file automatically.
       -  :code:`renderer.config.CsvExportFields = ["ID", "Title", "Office", "JobTitle"];` 
                   
    *  -  **BoxesCustomization**
       -  stores the customization for some single boxes. This is the key/value dictionary where the key is an ID of a box and the value is an object of box customization. Available fields for customization: **Orientation** – sets a box’s orientation. Can be “Stacked” or “Horizontal”. It has “Stacked” value by default. **Note**: BoxesCustomization works only for the TopToBottomCompact layout.
       -  .. code::
            
                renderer.config.BoxesCustomization = {
	                "6": {Orientation: "Horizontal"},
	                "3": {Orientation: "Horizontal"}
                }; 



Other properties can be defined in user interface of the configuration wizard, but you can override them also if required.