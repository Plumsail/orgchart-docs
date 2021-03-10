Version history – Office 365
============================

.. rubric:: 3.5.26

- Fix for CSS support in multi-page PDF reports.

.. rubric:: 3.5.25

- Fixes for applying custom localization from JavaScript. 
- Ability to set localization for layouts and orientation menus.
- Consider the filtration rule when calculating the number of subordinates in a box.

.. rubric:: 3.5.23

- Fixes for lines rendefing in multi-page PDF reports.
- Support of publishing pages by the feature with changing box orientation.
- Minor bugfixes.

.. rubric:: 3.5.20

- Ability to drill down to an assistant.
- Bug fix for Org Chart layout applied globally.
- Minor bugfixes.

.. rubric:: 3.5.18

- Ability to change the layout without opening the configuration wizard.
- Ability to change the orientation for specific boxes from stacked to horizontal and back.
- Bugfix for root employee autocomplete.
- Bugfix for reports generation in Internet Explorer.
- Minor bugfixes.

.. rubric:: 3.5.16

- Fixed incorrect rendering of vacancies for some scenarios.
- Fixed the bug with loading photos for users with an apostrophe in the account name.
- Minor bugfixes.


.. rubric:: 3.5.15

- The backend of the product has been rewritten from scratch.

.. rubric:: 3.2.34

- A bugfix for CSV export.


.. rubric:: 3.2.32

- Ability to export data from Org Chart to CSV file.


.. rubric:: 3.2.31

- Root employee selector with autocomplete in the configuration wizard.
- Multi-page report connection lines bugfix.
- Restricted ability to expand nodes in printing.
- Minor bugfixes.


.. rubric:: 3.2.29

- Ability to specify starting person, page orientation and page size for organizational structure reports.
- Minor bugfixes.


.. rubric:: 3.2.28

- New bottom to top layout.
- Minor bugfixes.


.. rubric:: 3.2.27

- Support of table of contents for multi-page reports.
- Minor bugfixes.


.. rubric:: 3.2.26

- Multi-page reports are implemented.


.. rubric:: 3.2.25

- New Modern skin with Office 365 site themes support.
- Bugfix for support of Number fields as employee ID in SharePoint list data source.


.. rubric:: 3.2.22

- New JavaScript method getNumberOfColumns for dynamically controlling number of columns based on current manager. It works only for "Top to bottom compact" layout.
- Bugfix for full screen mode. It didn’t work properly after recent Microsoft update.
- Bugfix for lines drawing.


.. rubric:: 3.2.20

- When root employee is excluded by filtration rule, it will be rendered anyway.
- Minor bugfixes.


.. rubric:: 3.2.19

- Added support of full-width web part mode on Modern pages.
- Improved license information caching.
- Fixed dotted lines manager connection lines and drill down button.
- Added support for zoom in for all layouts except "Left to right".
- Minor bugfixes.


.. rubric:: 3.2.16

- Added support for subscription based licensing.
- Minor bugfixes.


.. rubric:: 3.2.15

- Changed logic of boxes sorting for "Top to bottom compact" layout.
- Bugfix for displaying assistants in some specific cases.


.. rubric:: 3.2.14

- Support of Microsoft Teams desktop client.
- Ability to change search query pattern and query source for user profiles data source.


.. rubric:: 3.2.13

- Support of lookup values for SharePoint list data source. Now it is possible to display lookup value as well as lookup ID.
- Bugfix for displaying multiple assistants


.. rubric:: 3.2.12

- Ability to sort search results for user profiles data source.


.. rubric:: 3.2.10

- Migration of functionality from Office 365 version to On-Premises version.
- Support of A3 format in PDF export.
- Ability to expand up to 200 nodes automatically while printing.
- New JavaScript method "renderer.expandNodeLevelsConditionally" for conditional boxes expanding.


.. rubric:: 3.2.9

- JavaScript settings :code:`renderer.config.nodesSortOrder` and :code:`renderer.config.nodesSortOrder` are applied to assistants now.
- Bugfixes for assistant boxes lines rendering.


.. rubric:: 3.2.8

- Support for multiple assistants.
- Bugfix for full screen mode.
- Minor bugfixes.


.. rubric:: 3.2.7

- Fixed the bug with drawing connection lines for "Top to bottom compact" layout.
- Minor bugfixes.


.. rubric:: 3.2.6

- Support of "Person or Group" column in search for SharePoint list data source.
- Minor bugfixes.


.. rubric:: 3.2.5

- New feature for displaying dotted line manager on top of an employee with a solid line. It allows you to quickly navigate from solid box to a dotted-line manager.
- Added a new property to Org Chart JavaScript configuration that allows you to change the length of minimal search keyword (:code:`renderer.config.minSearchKeywordLenght`).


.. rubric:: 3.2.4

- Bugfix for resetting Org Chart configuration when SharePoint list is specified as a data source.
- Bugfix for dotted-line managers when search metadata property has a different name from user profile property.


.. rubric:: 3.2.3

- Ability to specify custom mappings for assistants and dotted line managers in user profiles data source.
- Ability for one user to have multiple dotted line managers.
- Minor bugfixes.


.. rubric:: 3.2.2

- Minor bugfixes on searching.


.. rubric:: 3.2.1

- Bugfix for displaying assistants and dotted-line subordinates.
- Ability to display fields with "TaxonomyFieldTypeMulti" type in templates.
- Improvements in connections lines rendering logic.
- Ability to hide connections lines for Org Chart loading improvements.
- Minor bugfixes.


.. rubric:: 3.2.0

- Bugfix for rendering Org Chart on publishing pages.


.. rubric:: 3.1.43

- Minor bugfixes.


.. rubric:: 3.1.42


- Search only by indexed column for SharePoint list.
- Fix for expanding button on mobile devices.
- Fix for profile’s pictures for users with the apostrophe in the account name.
- Support of MultiChoice, TaxonomyFieldType and LookupMulti field types.
- Fix the problem in the compact layout when the root element has only an assistant.
- Better error handling.
- Minor bugfixes.


.. rubric:: 3.1.41

- Fixed bug with rendering of the web part on Modern Communication sites.
- Other minor bugfixes.


.. rubric:: 3.1.40

- Improvements in web part localization logic.


.. rubric:: 3.1.37

- :code:`renderer.DrillDown` JavaScript framework method has been migrated from version 2
- Bugfix for zoom in Firefox
- Bugfix for full-screen mode after recent Microsoft update in "Modern UI"


.. rubric:: 3.1.35

- Ability to display level number inside a box
- Bugfix for a bug when printing freeze after multiple prints
- Minor bugfixes on boxes rendering


.. rubric:: 3.1.30

- Bugfix for displaying dotted-line subordinates


.. rubric:: 3.1.20

- New "top to bottom" compact layout


.. rubric:: 3.1.11

- Ability to display number of solid line subordinates inside boxes.


.. rubric:: 2.3.14

- Localization in On-Premises is now the same as in the Online version.
- Layouts are now the same in On-Prem and Online versions.
- Minor bugfixes.


.. rubric:: 2.3.13

- Bugfix for zoom functionality in Firefox browser.


.. rubric:: 2.3.12

- Bugfix for the rare case when user profiles service returns duplicate employees.


.. rubric:: 2.3.11

- Fix for the bug when box images are hidden after printing.


.. rubric:: 2.3.9

- Bugfix for rendering Org Chart on HTTPS sites.
- Bugfix to force JavaScript files cache clearing after upgrading solution.


.. rubric:: 2.3.8

- Bugfix for empty filtration rule.
- Bugfix for rendering Org Chart on a page with different ports.
- Other minor bugfixes.


.. rubric:: 2.3.7

- Client-side cache now supports clearing cache of managers structure for SharePoint list data source.


.. rubric:: 2.3.6

- Support for cross-domain printing of pictures without extensions.
- Added support of persisting of a box position after expanding\collapsing if possible.
- Minor connection lines rendering bugfixes.


.. rubric:: 2.3.4

- Support of displaying data from additional SharePoint list. It allows to map data to existing boxes.
- Bugfix for printing cross-domain pictures


.. rubric:: 2.3.3

- Support of fractional numbers in client side cache life time.
- Search autocomplete and jQuery UI conflict prevention improvements.
- Left to right layout bugfixes.
- Minor bugfixes.


.. rubric:: 2.3.1

- iPad touch bugfixes.
- Minor bugfixes.
- Update note: You may need to reactivate "Plumsail Org Chart" feature at site collection level.


.. rubric:: 2.2.33

- Fixed bug with support external lists as a data source.
- Minor bugfixes.


.. rubric:: 2.2.32

- Added new print system.
- Minor bugfixes.


.. rubric:: 2.2.28

- Dotted managers support.
- Vacancies support.
- Client side caching is implemented.
- New lines rendering engine.
- Automatic hiding of subordinate box if there is assistant box
- Minor bugfixes.


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
- External list as a data source bugfix.


.. rubric:: 2.0

- Office 365 version initial release.