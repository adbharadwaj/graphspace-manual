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
        "id": ... 
    },
    "position": { // Position Attributes
        "x": ...
        "y": ...
    }
}           
```

The `Node Object` describes a node in the graph. A `Node Object` typically contains two types of attributes:

#### 1. Node Data Attributes: An object specifying name-value pairs describing the node.
#### 2. Position Attributes: An object specifying the position of the node in the graph layout.

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
