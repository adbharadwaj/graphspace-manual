# Editing Layouts

GraphSpace provides powerful tools for the selection, movement, and organization of multiple nodes in a graph. The user can activate this functionality by clicking the `Use Layout Editor` button. 

## Start Tour 

The `Start Tour` button walks the user through all the features provided in the tool pallette. The Exit layout editor button gives a user the option to save the current layout and/or go back to the original view of the current graph. In the layout editor, the user may wield the tool pallette on the right hand side to quickly re-arrange the structure of the graph. 

## Edit selected nodes

A [GraphSpace](http://www.graphspace.org) user can change visual properties of a node by following the given steps:

1. Select one or more nodes either by [color](#select-by-color) or [shape](#select-by-shape) or using the [gestures](http://js.cytoscape.org/#notation/gestures) supported by Cytoscape.js.
2. Click on the `Edit selected nodes` button to launch the [node editor](#node-editor).
3. Change the visual properties of the selected nodes.
4. Click on `OK` if you want to save the changes else click on `Cancel` button to cancel the changes.

In the following example, the user is editing visual propeties of 'CTNNB1' node.

### Node Editor

GraphSpace that allows a user to select one or more nodes or edges based on [color](#select-by-color) and/or [shape](#select-by-shape), and to then change their visual properties using an easy-to-use interface. The current interface allows user to change the following properties:

1. **Color**: The background color of the node.
2. **Shape**: The shape of the node's body. GraphSpace currently supports following shapes - rectangle, roundrectangle, ellipse, triangle, pentagon, hexagon, heptagon, octagon, star, diamond, vee, or rhomboid.
3. **Width***: The width of the node’s body in pixels.
4. **Height***: The height of the node’s body in pixels.
5. **Label**: The label inside of node's body. In addition to specifying the value of a property outright, the developer may also use a [mapper to dynamically specify the property value](http://js.cytoscape.org/#style/mappers). For example, data(k) would map a property to the value in an element’s `k` data-attribute. This feature can used for visualizing node annotations in the layouts.

The following image shows the visual properties of a node before and after the editing using the node editor. In this example, user has made the following changes: (i) background color from green to pink (ii) shape from rectangle to ellipse (iii) width and height from 45px to 100px (iv) label from 'CTNNB1' to 'New Label'.

<table cellspacing="0">
<tr> 
   <td class="">
      <img src="_static/images/gs-screenshot-user1-node-editor-before edit.png" alt="Before editing"/>
   </td>               
   <td class="">
      <img src="_static/images/gs-screenshot-user1-node-editor-after edit.png" alt="After editing"/>
   </td> 
</tr>
<tr> 
   <th class="">
      Before.
   </th>               
   <th class="">
      After.
   </th> 
</tr>
</table>

When a user launches the node editor, it displays the values of style properties of the selected node if only one node is selected. Whereas if more than one node is selected, the node editor will display the values of style properties as blank. The following image shows an example of node editor when i) only one node is selected ii) more than one node is selected.




**Note:** When multiple nodes are selected and the user launches the node editor, the values for all properties are set to default. 

## Show node labels

Unchecking the `Show node labels` checkbox takes a user of GraphSpace to a simplified view of the graph that hides node names.

![toggle node labels](_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-toggle-node-labels-with-caption.gif)

## Select by shape

The `Select by shape` section allows the user to choose nodes in the graph based on nodes `shape` style property. For example, if a user wishes to select all nodes that are rectangles or ellipses, he/she will select both "Ellipse" and "Rectangle" in the tool pallete.

![select nodes by shape](_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-select-nodes-by-shape-with-caption.gif)

## Select by color

The `Select by color` section allows the user to choose nodes in the graph based on nodes `background-color` style property. For example, if a user wishes to select all nodes that are yellow or green, he/she will select both yellow and green.

![select nodes by color](_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-select-nodes-by-color-with-caption.gif)


## Unselect All Nodes

A user may click on the `Unselect All Nodes` button to reset all selections.

## Undo and Redo

The Undo and Redo buttons allow the user to undo or repeat all actions, including selection, editing and the arrange functions described below.

![undo redo changes](_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-arrange-nodes-undo-redo-with-caption.gif)


## Arrange nodes 

The `Arrange nodes` section allows a user to arrange all selected nodes into regions of different shapes. The following animation shows the arrangements of selected nodes that users may construct by clicking different buttons in this section.

<table cellspacing="0">
<tr> 
   <td class="">
      <img src="_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-arrange-nodes-open-circle-with-caption.gif" alt="Open Circle"/>
   </td>               
   <td class="">
      <img src="_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-arrange-nodes-closed-circle-with-caption.gif" alt="Closed Circle"/>
   </td> 
</tr>
<tr> 
   <td class="">
      <img src="_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-arrange-nodes-open-rectangle-with-caption.gif" alt="Open Rectangle"/>
   </td>               
   <td class="">
      <img src="_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-arrange-nodes-closed-rectangle-with-caption.gif" alt="Closed Rectangle"/>
   </td> 
</tr>
<tr> 
   <td class="">
      <img src="_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-arrange-nodes-vertical-with-caption.gif" alt="Vertical line"/>
   </td>               
   <td class="">
      <img src="_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-arrange-nodes-horizontal-with-caption.gif" alt="Horizontal line"/>
   </td> 
</tr>
<tr> 
   <td class="">
      <img src="_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-arrange-nodes-pinch-with-caption.gif" alt="Pinch"/>
   </td>               
   <td class="">
      <img src="_static/gifs/gs-screenshot-user1-wnt-pathway-reconstruction-arrange-nodes-expand-with-caption.gif" alt="Expand"/>
   </td> 
</tr>
</table>




