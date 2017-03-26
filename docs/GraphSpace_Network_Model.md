# GraphSpace Network Model

## CYJS Format

GraphSpace only supports one of the [Cytoscape.js supported](http://js.cytoscape.org/#notation/elements-json) JSON formats, which is:
```
{
    "elements":{  // Elements JSON
        "nodes":[ // List of Node Objects
            {  
                "data": { // Node Data Attributes
                    "id": ...
                },
                "position": { // Node Position Attributes
                    "x": ...
                    "y": ...
                }
            }, 
            .
            .
        ],
        "edges":[ // List of Edge Objects
            {
                "data": { // Edge Data Attributes
                    "source": ..., 
                    "target": ...
                }
            }, 
            .
            .
        ]
    },
    "data": {   // Graph Data Attributes
        "title": ...,       
        "tags": [..],       
        "description": ... 
    }
}
```

This [JSON (JavaScript Object Notation)](http://www.json.org/) format is defined by Cytoscape for storing network structure and data information. A Cytoscape (v3.1 or later) user can easily [export their graph](http://manual.cytoscape.org/en/stable/Cytoscape.js_and_Cytoscape.html#export-network-and-table-to-cytoscape-js) in above mentioned JSON format. We call the format as `CYJS format` because the extension of the exportable JSON file from Cytoscape App is `.cyjs`.

Any deviation from this format may result in GraphSpace rejecting the graph or problems in rendering the graph. For the sake of completeness, we have copied the description of several of the node and edge attributes directly from the [CytoscapeJS](http://js.cytoscape.org/) documentation. We thank them for the excellent documentation of their framework.

### Elements JSON

The elements JSON object contains two types of lists:

1.  List of Node Objects: An array of node objects describing the nodes in the graph.
2.  List of Edge Objects: An array of edge objects describing the edges in the graph.

### Graph Data Attributes

The `Graph Data Attributes` object specifies name-value pair describing the graph. The `Graph Data Attributes` are mapped to the Cytoscape network table for a network on import. Cytoscape supports `Graph Data Attributes` for both import and export.

#### Graph Data Attributes Attributes Treated Specially by GraphSpace

- required:

    - `name` – text – Name of the graph. It is later used for searching the graph in GraphSpace.
    - `tags` – list of strings – Used to categorize graphs. See Tags for more information.
    - `description` – text – May be HTML formatted string. May be link to image hosted elsewhere. May simly be a string which contains information such as a legend or significance of the graph.
    
- optional:

    - `title` – text – Name that is displayed on top of graph while viewing it.
    
**Note:** The user can use add more data attributes to embed information about the graph. If the attributes are not specially treated by GraphSpace, they will be treated as "opaque". This means that GraphSpace will store or transmit the data without any processing.
    
### Node Object

```
{
    "data": {     // Node Data Attributes
        "id": ... // unique identifier for the node
    },
    "position": { // Position Attributes
        "x": ...
        "y": ...
    }
}           
```

The `Node Object` describes a node in the graph. A `Node Object` typically contains two types of attributes:

1. **Node Data Attributes**: 
    
    Node Data Attributes specify name-value pairs describing the node. Cytoscape requires that each Node Object should have an  `id` data attribute which can uniquely identify the element in the graph. The users can define more data-attributes to describe the node. But, if the attributes are not specially treated by GraphSpace, they will be treated as "opaque". This means that GraphSpace will store or transmit the data without any processing. Please refer to list of node data attributes treated specially by GraphSpace to make the best use of GraphSpace's features.
    
2. **Position Attributes**: 
    
    Position Attributes specify the [model position](http://js.cytoscape.org/#notation/position) of the node in the graph layout. For example, `{ x: 100, y: 100 }` specifies a point 100 pixels to the right and 100 pixels down from the top-left corner of the viewport at zoom 1 and pan (0,0).
    
### Edge Object

```
{
    "data": {     // Node Data Attributes
        "source": ..., // identifier for the source node
        "target": ...  // identifier for the target node
    }
}           
```

The `Edge Object` describes a node in the graph. An `Edge Object` typically contains a data object which is defined as following:

- **Edge Data Attributes**: 
    
    Edge Data Attributes specify name-value pairs describing the edge. Cytoscape requires that each Edge Object should have  `source` and `target` data attributes which can respectively identify the source and target nodes for the edge in the graph. The users can define more data-attributes to describe the edge. But, if the attributes are not specially treated by GraphSpace, they will be treated as "opaque". This means that GraphSpace will store or transmit the data attributes without any processing. Please refer to list of edge data attributes treated specially by GraphSpace to make the best use of GraphSpace's features.
    
#### Node Data Attributes Attributes Treated Specially by GraphSpace

- required:

    - `id` – text – A unique id representing the node.
    
- optional:

    - `label` – text – The text that is displayed inside of the node.
    - `popup` - text - A string that will be displayed in a popup window when the user clicks the node. This string can be HTML-formatted.
    - `k` - integer -An integer index for this node. GraphSpace uses this attribute when the user seeks to step through the nodes and edges of the graph.
    
**Note:** The user can use add more data attributes to embed information about the node. But, if the attributes are not specially treated by GraphSpace, they will be treated as "opaque". This means that GraphSpace will store or transmit the data without any processing.


#### Edge Data Attributes Attributes Treated Specially by GraphSpace

- required:

    - `source` – text – The id of the node where the edge is coming from.
    - `target` – text – The id of the node where edge is going to.
    
- optional:

    - `popup` - text - A string that will be displayed in a popup window when the user clicks the edge. This string can be HTML-formatted.
    - `k` - integer - An integer index for this node. GraphSpace uses this attribute when the user seeks to step through the nodes and edges of the graph.
    
**Note:** The user can use add more data attributes to embed information about the edge. But, if the attributes are not specially treated by GraphSpace, they will be treated as "opaque". This means that GraphSpace will store or transmit the data without any processing.


The overall structure of CYJS formatted JSON file looks like the following sample structure:
```
{
    "elements":{  
        "nodes":[ // list of graph nodes 
            {
                "data": { // data-attributes specify name-value pairs describing the node.
                    "id": ... // identifier for the node
                },
                "position": { // can optionally specify position of the node.
                    "x": ...
                    "y": ...
                }
            }, 
            .
            .
        ],
        "edges":[ // list of graph edges 
            {
                "data": { // data-attributes specify name-value pairs describing the edge.
                    "source": ..., // identifier for the source node
                    "target": ...  // identifier for the target node
                }
            }, 
            .
            .
        ]
    },
    "data": { // data-attributes specify name-value pairs describing the graph.
        "title": ...,       // title for the graph
        "tags": [..],       // list of tags for the graph,
        "description": ...  // description for the graph e.g., legend
    }
}
```

## Stylesheet JSON Format

Cytoscape and Cytoscape.js are sharing a concept called [Style](http://manual.cytoscape.org/en/stable/Cytoscape.js_and_Cytoscape.html#export-styles-to-cytoscape-js). This is a collection of mappings from data point to network property. Cytoscape can export its Styles into CSS-based Cytoscape.js JSON. 

A Cytoscape (v3.1 or later) user can export all Styles into one JSON file from **File | Export | Style** and select Cytoscape.js JSON as its format.

**Note:** Cytoscape.js [does not support all of Cytoscape Network Properties](
http://manual.cytoscape.org/en/stable/Cytoscape.js_and_Cytoscape.html#limitations). Those properties will be ignored or simplified when you export to JSON Style file.
