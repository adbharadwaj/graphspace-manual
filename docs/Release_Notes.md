# Release Notes

## [GraphSpace 2.0]()

### Highlights

- We have added features in the layout editor that allow a user to select nodes and edges based
on color and shape in order to edit their visual properties. This functionality is available in
conjunction with the features that allowed a user to arrange the positions of the nodes in a
variety of shapes.
- We have brought the JSON format accepted by GraphSpace in line with Cytoscape.js (this
JSON format is also compatible with Cytoscape).
    (a) We separate the structure of the network (nodes and edges) from the description of the
visual styles of the nodes and edges.
(b) Cytoscape.js supports a network-level \data" section in the JSON le specifying the
network structure. We allow users to include network-specic attributes in this section,
e.g., \PMID", \authors", and \organism".
(c) Cytoscape.js supports a \data" section within each node. Currently, GraphSpace
recognizes an attribute called \aliases" in this section, through which the network creator
can specify a list of aliases for the node.
(d) GraphSpace now supports CSS-based Cytoscape.js JSON les for specifying the style
of the graph. GraphSpace users can import these les either in the \Upload" section
or the \Layout Editor" section.
(e) We have deprecated support for the JSON format supported only by GraphSpace.
3. We have streamlined the search interface and made it more ecient. We have added support
to search for networks that match a specic attribute (key-value pair) in addition to nodes.



## [GraphSpace 1.1](https://github.com/Murali-group/GraphSpace/releases/tag/v1.0)

## [GraphSpace 1.0]()
