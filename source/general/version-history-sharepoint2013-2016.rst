Version history – SharePoint 2013/2016 version
==============================================



.. rubric:: 3.5.17

Bug fix for root employee autocomplete.
Bug fix for reports generation in Internet Explorer.
Minor bug fixes.


.. rubric:: 3.5.16

- Bug fix for toolbar icons font broken in Internet Explorer.


.. rubric:: 3.2.37

- Support of the table of contents in multi-page PDF reports
- Minor bug fixes.


.. rubric:: 3.2.36

- Ability to change layout without opening the configuration wizard.
- Minor bug fixes.


.. rubric:: 3.2.35

Migration of new features from Office 365 version:

- Modern skin.
- Multi-page reports. The table of contents is not supported yet.
- Ability to export data from Org Chart to CSV file.
- New bottom to top layout.
- Root employee selector with autocomplete in the configuration wizard.
- Ability have multiple dotted-line managers.
- Ability have multiple assistants managers.
- Restricted ability to expand nodes in printing.


.. rubric:: 3.2.33

- Prevented conflicts with a third-party app that uses Knockout.js.
- Added logic to load fresh JavaScript files after the web part update.


.. rubric:: 3.2.21

- Added the new license check page.


.. rubric:: 3.2.18

- Added support for new server ID generator for unified license protection.


.. rubric:: 3.2.16

- Added support for subscription based licensing.
- Minor bug fixes.


.. rubric:: 3.2.15

- Changed logic of boxes sorting for “Top to bottom compact” layout.
- Bug fix for displaying assistants in some specific cases.


.. rubric:: 3.2.14

- Support of Microsoft Teams desktop client.
- Ability to change search query pattern and query source for user profiles data source.


.. rubric:: 3.2.13

- Support of lookup values for SharePoint list data source. Now it is possible to display lookup value as well as lookup ID.
- Bug fix for displaying multiple assistants in Org Chart for 2013/2016 version


.. rubric:: 3.2.12

- Ability to sort search results for user profiles data source.


.. rubric:: 3.2.10

- Migration of functionality from Office 365 version to On-Premises version.
- Support of A3 format in PDF export.
- Ability to expand up to 200 nodes automatically while printing.
- New JavaScript method “renderer.expandNodeLevelsConditionally” for conditional boxes expanding.


.. rubric:: 3.2.9

- JavaScript settings “renderer.config.nodesSortOrder” and “renderer.config.nodesSortOrder” are applied to assistants now.
- Bug fixes for assistant boxes lines rendering.


.. rubric:: 3.2.8

- Support for multiple assistants.
- Bug fix for full screen mode.
- Minor bug fixes.


.. rubric:: 3.2.7

- Fixed the bug with drawing connection lines for “Top to bottom compact” layout.
- Minor bug fixes.


.. rubric:: 3.2.6

- Support of “Person or Group” column in search for SharePoint list data source.
- Minor bug fixes.


.. rubric:: 3.2.5

- New feature for displaying dotted line manager on top of an employee with a solid line. It allows you to quickly navigate from solid box to a dotted-line manager.
- Added a new property to Org Chart JavaScript configuration that allows you to change the length of minimal search keyword (renderer.config.minSearchKeywordLenght).


.. rubric:: 3.2.4

- Bug fix for resetting Org Chart configuration when SharePoint list is specified as a data source.
- Bug fix for dotted-line managers when search metadata property has a different name from user profile property.


.. rubric:: 3.2.3

- Ability to specify custom mappings for assistants and dotted line managers in user profiles data source.
- Ability for one user to have multiple dotted line managers.
- Minor bug fixes.


.. rubric:: 3.2.2

- Minor bug fixes on searching.


.. rubric:: 3.2.1

- Bug fix for displaying assistants and dotted-line subordinates.
- Ability to display fields with “TaxonomyFieldTypeMulti” type in templates.
- Improvements in connections lines rendering logic.
- Ability to hide connections lines for Org Chart loading improvements.
- Minor bug fixes.


.. rubric:: 3.2.0

- SharePoint 2013/2016 version:
- Bug fix for rendering Org Chart on publishing pages.


.. rubric:: 3.1.43

- Minor bug fixes.


.. rubric:: 3.1.42

- Search only by indexed column for SharePoint list.
- Fix for expanding button on mobile devices.
- Fix for profile’s pictures for users with the apostrophe in the account name.
- Support of MultiChoice, TaxonomyFieldType and LookupMulti field types.
- Fix the problem in the compact layout when the root element has only an assistant.
- Better error handling.
- Minor bug fixes.


.. rubric:: 3.1.41

- Fixed bug with rendering of the web part on Modern Communication sites.
- Other minor bug fixes.


.. rubric:: 3.1.40

- Improvements in web part localization logic.


.. rubric:: 3.1.37

- renderer.DrillDown JavaScript framework method has been migrated from version 2
- Bug fix for zoom in Firefox
- Bug fix for full-screen mode after recent Microsoft update in “Modern UI”


.. rubric:: 3.1.35

- Ability to display level number inside a box
- Bug fix for a bug when printing freeze after multiple prints
- Minor bug fixes on boxes rendering


.. rubric:: 3.1.30

- Bug fix for displaying dotted-line subordinates


.. rubric:: 3.1.20

- New “top to bottom” compact layout


.. rubric:: 3.1.11

- Ability to display number of solid line subordinates inside boxes.


.. rubric:: 2.4.2

- These features were migrated to SharePoint 2013/2016 version from Office 365 version:

- Search only by indexed column for SharePoint list.
- Ability to display level number inside a box.
- Ability to display number of solid line subordinates inside boxes.

New features:

- Improvements for printing performance.
- Ability to search in Lookup columns for SharePoint list.
- Bug fix of getting a vacancies list if the user doesn’t have “Full control” permissions.
- Bug fix for the bug when a search doesn’t work for large lists even with indexed columns.
- Minor bug fixes.


.. rubric:: 2.3.14

- Localization in On-Premises is now the same as in the Online version.
- Layouts are now the same in On-Prem and Online versions.
- Minor bug fixes.


.. rubric:: 2.3.13

- Bug fix for license checking on SharePoint 2013/2016 servers with rewrite enabled.
- Bug fix for zoom functionality in Firefox browser.


.. rubric:: 2.3.12

- Bug fix for the rare case when user profiles service returns duplicate employees.


.. rubric:: 2.3.11

- Fix for the bug when box images are hidden after printing.


.. rubric:: 2.3.10

- Bug fix of displaying vacancies in SharePoint 2013/2016 version.


.. rubric:: 2.3.9

- Bug fix for rendering Org Chart on HTTPS sites.
- Bug fix to force JavaScript files cache clearing after upgrading solution.


.. rubric:: 2.3.8

- Bug fix for empty filtration rule.
- Bug fix for rendering Org Chart on a page with different ports.
- Other minor bug fixes.


.. rubric:: 2.3.7

- Client-side cache now supports clearing cache of managers structure for SharePoint list data source.


.. rubric:: 2.3.6

- Support for cross-domain printing of pictures without extensions.
- Added support of persisting of a box position after expanding\collapsing if possible.
- Minor connection lines rendering bug fixes.


.. rubric:: 2.3.5

- Support of cross-domain pictures for png printing in SharePoint 2013/2016 version.
- Minor bug fixes.


.. rubric:: 2.3.4

- Support of displaying data from additional SharePoint list. It allows to map data to existing boxes.
- Bug fix for printing cross-domain pictures


.. rubric:: 2.3.3

- Support of fractional numbers in client side cache life time.
- Search autocomplete and jQuery UI conflict prevention improvements.
- Left to right layout bug fixes.
- Minor bug fixes.


.. rubric:: 2.3.1

- iPad touch bug fixes.
- Minor bug fixes.

Update note: You may need to reactivate “Plumsail Org Chart” feature at site collection level.


.. rubric:: 2.2.33

- Fixed bug with support external lists as a data source.
- Minor bug fixes.


.. rubric:: 2.2.32

- Added new print system.
- Minor bug fixes.


.. rubric:: 2.2.28

- Dotted managers support.
- Vacancies support.
- Client side caching is implemented.
- New lines rendering engine.
- Automatic hiding of subordinate box if there is assistant box
- Minor bug fixes.


.. rubric:: 2.2.12

- Left to right layout implemented.
- Configuration wizard rendering optimization.
- Assistant boxes take less space now.


.. rubric:: 2.2.11

- Caching API for user profiles data source.
- Double search for user profiles data source. Use search service if available, otherwise use user profile service search.


.. rubric:: 2.2.10

- Root node double tooltip for nodes with assistants fixed.
- URL field support added to SharePoint list data source.


.. rubric:: 2.2.4

- Assistants support.
- External list as a data source bug fix.


.. rubric:: 2.0

- Initial release of SharePoint 2013/2016 version.
- Rendering engine has been completely rewritten from SharePoint 2010.