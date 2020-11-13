How to export SharePoint Org Chart to CSV
========================================================================

You may wish to view all members of your Organization in a spreadsheet format. 
The best way to achieve this is to have an orderly sequential list of members in **CSV** form usable in MS Excel, LibreOffice Calc, Google Sheets, Numbers for MacOS and similar software.


How to export to CSV
--------------------

Open a page where with an Org Chart web part. In the up-right corner, there is a **settings** wheel icon—click it and choose the **Export to CSV** option.

.. image:: /../_static/img/how-tos/printing-and-reports/export-to-csv-and-analyze-in-excel/export_to_csv_button-e1587542299353.png
    :alt: Export to CSV

You will see the following menu:

.. image:: /../_static/img/how-tos/printing-and-reports/export-to-csv-and-analyze-in-excel/export-to-csv-menu.png
    :alt: Export to CSV menu


You can specify the following to achieve a better result:

- **Start from this person** to pick a manager that you want "on top" of the export data. The resulting CSV will contain this manager and all the employees below. If you live this field blank, the `root employee <../configuration-wizard/filtration.html>`_  you’ve picked up in the Configuration wizard will be selected by default. 
Just start typing a name to get a list of suggestions:

.. image:: /../_static/img/how-tos/printing-and-reports/export-to-csv-and-analyze-in-excel/export-to-csv-start-typing.png
    :alt: Export to CSV


- **Levels to collect** to specify how deep you want the data to go down from the selected manager. The resulting CSV will have all the employees for the selected number of levels.

- **CSV delimiter** to chose either a semicolon or a comma to use as a separator.


If you wish to export all the members of your organization, just select the maximum number levels. If you don’t know the precise number of levels in your organization, just type in a large number, for example, 1000.


How to work with the data
-------------------------

Most of the spreadsheed editors will recognize and open the CSV file automatically. You can open the resulting CSV file in any spreadsheet editor, for example, MS Excel.

You will see a list of employees with all the info from the `Box template <../configuration-wizard/box-template.html>`_ and the `Tooltip tamplate <../configuration-wizard/tooltip-template.html>`_ plus some additional fields that you might need for analytic purposes:

- **AccountName** contains the SharePoint account of the person. If you use a SharePoint list as a Data Source, you will see **item ID** instead.
- **Manager** contains the SharePoint account of the person’s manager. If you use a SharePoint list as a Data Source, you will see the manager’s **item ID** instead.
- **PochLevelNumber** contains the level number of the person starting from the root employee.
- **PochSubordinatesCount** contains the number of the person’s subordinates in total.

.. image:: /../_static/img/how-tos/printing-and-reports/export-to-csv-and-analyze-in-excel/export-to-csv-data-example.png
    :alt: Export to CSV

For example, you can view and analyse tha Managers / Employees ration in your Organization:

.. image:: /../_static/img/how-tos/printing-and-reports/export-to-csv-and-analyze-in-excel/export_to_csv_graph1.png
    :alt: Export to CSV

Or you can visualize your employees per level:

.. image:: /../_static/img/how-tos/printing-and-reports/export-to-csv-and-analyze-in-excel/export_to_csv_graph2.png
    :alt: Export to CSV


Find more examples in `this article <../configuration-wizard/box-template.html>`_.