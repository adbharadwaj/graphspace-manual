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

![Graph Upload Form](_static/images/gs-screenshot-upload-graph-form.png)

We support the following types of files:

- Graphs that a user of Cytoscape (v3.1 or later) can export in a JSON format, which we call "cyjs" format. 
- Please follow [these instructions](https://github.com/idekerlab/cy-net-share/wiki) to export your Cytoscape graph to this format. These files must use the .cyjs extension.


If a user has an account and is logged in, this interface will upload the graph directly into the user's account, much like using the REST API. If a user does not have an account or is not logged in, this upload functionality will provide a unique URL through which the user may interact with the graph represented by the uploaded file. **Note: After 30 days, we will delete all graphs that are uploaded for unregistered users of GraphSpace.**

