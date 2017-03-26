# Uploading Graphs

There are 4 different ways of creating networks in Cytoscape:

Importing pre-existing, fixed-format network files.
Importing pre-existing, unformatted text or Excel files.
Importing data from from public databases.
Creating an empty network and manually adding nodes and edges.

GraphSpace provides 2 different ways to upload graphs: 

- Via the REST API 
- Via the Web Interface

## Via the REST API

GraphSpace users can also upload graphs using GraphSpace's REST API. Please refer to the Programmer's Guide for more information.

## Via the Web Interface

As an alternative to the REST API for uploading a graph, we provide a simple web interface for uploading individual graphs. 

<a href="#graph-upload-form"> <img src="_static/images/gs-screenshot-upload-graph-form.png" width="48", alt="Graph Upload Form"></a>

The upload graph form has three input fields:

### Graph Name 

The name of the graph. GraphSpace allows users to search graphs by their name.
### Network File 

The network file in [JSON (JavaScript Object Notation)](http://www.json.org/) format defined by Cytoscape. A Cytoscape (v3.1 or later) user can [export their graph](http://manual.cytoscape.org/en/stable/Cytoscape.js_and_Cytoscape.html#export-network-and-table-to-cytoscape-js) in the JSON format. Since the extension of exportable JSON file from Cytoscape is `.cyjs`, we call the format as `CYJS` format in the rest of the documentation.


### Style File 

Cytoscape and Cytoscape.js are sharing a concept called [Style](http://manual.cytoscape.org/en/stable/Cytoscape.js_and_Cytoscape.html#export-styles-to-cytoscape-js). This is a collection of mappings from data point to network property. Cytoscape can export its Styles into CSS-based Cytoscape.js JSON. 

A Cytoscape (v3.1 or later) user can export all Styles into one JSON file from **File | Export | Style** and select Cytoscape.js JSON as its format.

**Note:** Cytoscape.js [does not support all of Cytoscape Network Properties](
http://manual.cytoscape.org/en/stable/Cytoscape.js_and_Cytoscape.html#limitations). Those properties will be ignored or simplified when you export to JSON Style file.


If a user has an account and is logged in, this interface will upload the graph directly into the user's account, much like using the REST API. If a user does not have an account or is not logged in, this upload functionality will provide a unique URL through which the user may interact with the graph represented by the uploaded file. **Note: After 30 days, we will delete all graphs that are uploaded for unregistered users of GraphSpace.**

