How to localize Org Chart in SharePoint and Microsoft Teams
===========================================================

Org Chart allows changing strings in the user interface since version 2.2.30. You can use this functionality to translate user interface to your language.

.. note:: You may find the full structure of the localization object at the end of this article.

.. note:: If the version of your Org chart is earlier than 2.3.14 you should use this :ref:`instruction`.

The picture below will help you to understand the structure of the localization strings:

.. image:: /../_static/img/how-tos/customize-boxes-and-styles/localize-orgchart/localization-strings.png
    :alt: Localization strings


You need to open the configuration wizard and navigate to the `Custom JavaScript <../configuration-wizard/custom-javascript.html>`_ step. 
Then you can override strings like this:

.. code-block:: javascript

   Plumsail.OrgChart.LocalizationStrings.SearchInputWatermark = "Suche";
   Plumsail.OrgChart.LocalizationStrings.Settings.PrintOrgChart.Title = "Drucken";
   Plumsail.OrgChart.LocalizationStrings.Settings.ManageVacancies = "Stellenangebote";
   Plumsail.OrgChart.LocalizationStrings.Settings.ClearCache = "Cache leeren";
   Plumsail.OrgChart.LocalizationStrings.Settings.Help = "Über";


.. image:: /../_static/img/how-tos/customize-boxes-and-styles/localize-orgchart/ChangeLocalizationStrings.png
    :alt: Change Localization Strings


.. note:: You may need to refresh the page to apply changes.


This is the structure of the localization object. Read through the comments in the object to understand the purpose of each property.

.. code-block:: javascript

  {
    SearchInputWatermark: "Search", //This message appears inside search box
    PeoplePickerWatermark: "Start typing...", //This message appears inside people pickers
    RightControlZone: { //Buttons section located at the right top corner
      OriginalZoom: "", //Hint text for original zoom button
      FullScreenMode: "", //Hint text for full screen button
      Settings: "", //Hint text for settings button (gears icon)
      Layouts: "" //Hint text for layouts button
    },
    LayoutsMenu: {
        TopToBottomCompact: "Top to bottom compact",
        TopToBottomClassic: "Top to bottom classic",
        TopToBottomWithGroupingLeafBoxes: "Top to bottom with grouping of leaf boxes",
        LeftToRight: "Left to right",
        BottomToTop: "Bottom to top"
    },
    Settings: {
      Settings: { //Settings menu which is opened when you click on gears icon
        Settings: "", //Configuration wizard menu item text
        PrintOrgChart: { //Strings related to printing
          Title: "", //Text for print menu item
          PrintingIsNotSupported: "Printing in Firefox, Internet Explorer 9 and below is not supported. Please use Internet Explorer 10 and later, Chrome or Safari. If you use IE 10 and above and see this message, then your browser is in compatibility mode of IE 9 and below.",
          ExportDialog: {
            Title: "Print",
            SubTitle: "Print currently visible employees.",
            ExportAsLabel: "Output format",
            PaperSizeLabel: "Paper size",
            LandscapeLabel: "Landscape",
            NoOptionsDescription: "Paper size and layout will be adjusted automatically.",
            ExportButton: "Print",
            CancelButton: "Cancel"
          },
          ProcessingPdfPanel: {
            ProcessingMessage: "Generating PDF may take a few minutes.",
            ReadyMessage: "Your PDF is ready!",
            CancelConfirmMessage: "Are you sure you want to cancel the operation?",
            ErrorMessage: "Error occurred during PDF generation. Please contact support@plumsail.com",
            DownloadButton: "Download",
            OkButton: "Ok",
            CancelButton: "Cancel"
          },
          ProcessingPngPanel: {
            ProcessingMessage: "Generating PNG may take a few minutes.",
            ReadyMessage: "Your PNG is ready!",
            CancelConfirmMessage: "Are you sure you want to cancel the operation?",
            ErrorMessage: "Error occurred during PNG generation. Please contact support@plumsail.com",
            DownloadButton: "Download",
            OkButton: "Ok",
            CancelButton: "Cancel"
          }
        },
        GenerateReport: {
          Title: "Generate report",
          ReportDialog: {
            Title: "Organization report",
            SubTitle: "Generate multi-page report of your organization.",
            StartPersonLabel: "Start report from this person",
            LevelsToCollectLabel: "Levels to collect",
            PaperSizeLabel: "Paper size",
            LandscapeLabel: "Landscape",
            StartPersonValidationMessage: "Specify starting person or keep it empty to start from the currently displayed employee.",
            GenerateButton: "Generate",
            CancelButton: "Cancel"
          },
          ProcessingPanel: {
            ProcessingMessage: "Generating report may take a few minutes.",
            ReadyMessage: "Your report is ready!",
            CancelConfirmMessage: "Are you sure you want to cancel the operation?",
            ErrorMessage: "Error occurred during report generation. Please contact support@plumsail.com",
            DownloadButton: "Download",
            OkButton: "Ok",
            CancelButton: "Cancel"
          }
        },
        ExportCsv: {
          Title: "Export to CSV",
          ExportDialog: {
            Title: "Export to CSV",
            StartPersonLabel: "Start from this person",
            LevelsToCollectLabel: "Levels to collect",
            DelimiterLabel: "CSV delimiter",
            CommaDelimiterLabel: "Comma",
            SemicolonDelimiterLabel: "Semicolon",
            StartPersonValidationMessage: "Specify starting person or keep it empty to start from the currently displayed employee.",
            ExportButton: "Export",
            CancelButton: "Cancel"
          },
          ProcessingPanel: {
            ProcessingMessage: "Generating CSV may take a few minutes.",
            ReadyMessage: "Your CSV is ready!",
            CancelConfirmMessage: "Are you sure you want to cancel the operation?",
            ErrorMessage: "Error occurred during CSV generation. Please contact support@plumsail.com",
            DownloadButton: "Download",
            OkButton: "Ok",
            CancelButton: "Cancel"
          }
        },
        ManageVacancies: "", //Manage vacancies menu item text
        ClearCache: { //Strings related to cache clearing
          Title: "", //Text for clear cach menu item
          ClearCacheConfirmMessage: "" //Text for clear cache confirmation message box
        },
        Help: "" //Help menu item text
      },
      BoxOrientationMenu: {
        StackedOrientation: "Stacked orientation",
        HorizontalOrientation: "Horizontal orientation"
      },
      DrillDownToolbar: { //Toolbar which appears on hove over org chart boxes
        GoToParent: "", //Hint text for go to parent button
        GoToRoot: "", //Hint text for go to root button
        DrillHere: "", //Hint text for drill here button
      },
      ChangeBoxOrientationConfirmMessage: "We are going to increase <a target='_blank' href='https://plumsail.com/sharepoint-orgchart/docs/the-maximum-number-of-columns-in-the-compact-layout'>the maximum number of columns</a> in your layout from {0} to {1}.",
      UserProfilePropertyNames: {
        "UserProfile_GUID": "Id",
        "SID": "SID",
        "ADGuid": "Active Directory Id",
        "AccountName": "Account name",
        "FirstName": "First name",
        "SPS-PhoneticFirstName": "Phonetic First Name",
        "LastName": "Last name",
        "SPS-PhoneticLastName": "Phonetic Last Name",
        "PreferredName": "Name",
        "SPS-PhoneticDisplayName": "Phonetic Display Name",
        "WorkPhone": "Work phone",
        "Department": "Department",
        "Title": "Title",
        "SPS-JobTitle": "Job Title",
        "Manager": "Manager",
        "AboutMe": "About me",
        "PersonalSpace": "Personal site",
        "PictureURL": "Picture",
        "UserName": "User name",
        "QuickLinks": "Quick links",
        "WebSite": "Web site",
        "PublicSiteRedirect": "Public site redirect",
        "SPS-DataSource": "Data source",
        "SPS-MemberOf": "MemberOf",
        "SPS-Dotted-line": "Dotted-line Manager",
        "SPS-Peers": "Peers",
        "SPS-Responsibility": "Ask Me About",
        "SPS-SipAddress": "SIP Address",
        "SPS-MySiteUpgrade": "My Site Upgrade",
        "SPS-DontSuggestList": "Don’t Suggest List",
        "SPS-ProxyAddresses": "Proxy addresses",
        "SPS-HireDate": "Hire date",
        "SPS-DisplayOrder": "Display Order",
        "SPS-ClaimID": "Claim User Identifier",
        "SPS-ClaimProviderID": "Claim Provider Identifier",
        "SPS-ClaimProviderType": "Claim Provider Type",
        "SPS-LastColleagueAdded": "Last Colleague Added",
        "SPS-OWAUrl": "Outlook Web Access URL",
        "SPS-SavedAccountName": "Saved Account Name",
        "SPS-SavedSID": "Saved SID",
        "SPS-ResourceSID": "Resource Forest SID",
        "SPS-ResourceAccountName": "Resource Forest Account Name",
        "SPS-ObjectExists": "Object Exists",
        "SPS-MasterAccountName": "Master Account Name",
        "SPS-DistinguishedName": "Distinguished Name",
        "SPS-SourceObjectDN": "Source Object Distinguished Name",
        "SPS-LastKeywordAdded": "Last Keyword Added",
        "WorkEmail": "Work e-mail",
        "CellPhone": "Mobile phone",
        "Fax": "Fax",
        "HomePhone": "Home phone",
        "Office": "Office",
        "SPS-Location": "Office Location",
        "SPS-TimeZone": "Time Zone",
        "Assistant": "Assistant",
        "SPS-PastProjects": "Past projects",
        "SPS-Skills": "Skills",
        "SPS-School": "Schools",
        "SPS-Birthday": "Birthday",
        "SPS-StatusNotes": "Status Message",
        "SPS-Interests": "Interests",
        "SPS-EmailOptin": "Email Notifications"
      }
    }
  };

.. _instruction:

Localization in Org Chart for SharePoint 2013/2016
--------------------------------------------------

Just find **Localization.js** file located in the Style Library of your site collection. 
The URL to find it looks like this **http://YOUR_SITE_COLLECTION/Style Library/Plumsail/OrgChart**.

Then change any string and save the file. Your changes will appear in the web part interface. 
If you leave values blank, the web part will use default values.

.. note:: Do not forget to check in and publish the file if publishing is enabled in your **Style Library**.
