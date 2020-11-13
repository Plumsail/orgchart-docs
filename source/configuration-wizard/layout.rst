Default Layout
==============

.. rubric:: Setting the Layout

At this step you can choose a default layout that will be displayed for all the users when they open the page with the Org Chart web part for the first time.

.. image:: /../_static/img/advanced-web-part-configuration/layout/OrgChart-Configuration-Wizard-4.png
    :alt: Layout

Your users can choose a different layout to get a better visualization for their needs.

.. image:: /../_static/img/advanced-web-part-configuration/layout/Layout1.gif
    :alt: Layout

This choice will be remembered for the current user only and will not affect other users.

Layout Descriptions
-------------------

.. rubric:: Top to bottom compact

This layout is perfect if you want to keep "top to bottom" layout and fit wide structures in a smaller area. 
You can set the maximum number of columns you want your Org Chart to fit. 
If the number of boxes on the second level exceeds the maximum, the boxes will be stacked. 
The boxes on the third and subsequent levels are always stacked under the corresponding boxes on the second level to keep the fixed width of the structure.


In this example, the maximum number of columns is set to three. If the number of boxes on the second level is equal to or less than three, the level lines up horizontally:


.. image:: /../_static/img/advanced-web-part-configuration/layout/Top-to-bottom-compact-0.png
    :alt: Top to bottom compact


If the number of boxes on the second level is greater than three, the boxes are stacked in three columns:

.. image:: /../_static/img/advanced-web-part-configuration/layout/Top-to-bottom-compact-2.png
    :alt: Top to bottom compact


You can change the layout behavior to combine both horizontal and stacked orientations to better reflect your organization structure:

1. Open your page in edit mode
2. If the Top-to-bottom compact layout is chosen, you will see a gear icon in the top-left corner of each box on the second level. Click on it to select the orientation.

.. image:: /../_static/img/advanced-web-part-configuration/layout/Top-to-bottom-orientation.gif
    :alt: Top to bottom orientation


You can drill down to any box by clicking on the down-arrow icon that appears on top of each box when you hover with a cursor. Then you can change the orientation for any box that is now on the second level too. This orientation will be saved for the current box.


.. Note:: changing the settings for the Top to bottom compact layout will affect all the users who use the layout.


.. rubric:: Top to bottom with grouping of leaf boxes

This is a modification of a classic "top to bottom" layout. The only difference is that all leaf boxes (employees without subordinates) are joined into a two column group on the right-hand side.


.. image:: /../_static/img/advanced-web-part-configuration/layout/example-group-leaf-nodes.png
    :alt: Example group leaf nodes


.. rubric:: Top to bottom classic

Top to bottom is a classic tree org chart layout.

.. image:: /../_static/img/advanced-web-part-configuration/layout/example-top-to-bottom.png
    :alt: Example top to bottom


.. rubric:: Bottom to top

The inverted version of the Top to bottom layout. The root item is displayed on the bottom of the Chart.

.. image:: /../_static/img/advanced-web-part-configuration/layout/bottom_to_top_layout-e1576176982794.png
    :alt: Bottom to top


.. rubric:: Left to right layout

Left to right layout is good when you want to display all boxes stacked as a file system tree.


.. image:: /../_static/img/advanced-web-part-configuration/layout/example-left-to-right.png
    :alt: Example left to right


.. Note:: Go to the next step of the advanced configuration wizard `General settings <../configuration-wizard/general-settings.html>`_ .
  