# Programmers Guide

## GraphSpace REST API

The GraphSpace REST API provides API endpoints for GraphSpace entities like graphs, layouts and groups that allow developers to interact with the GraphSpace website remotely by sending and receiving JSON (JavaScript Object Notation) objects. JSON is a lightweight and human-readable open standard data format. It looks like Objects in JavaScript; hence the name. When you send content to or make a request to the API, the response will be returned in JSON. This enables developers to create, read and update GraphSpace content from client-side JavaScript or from external applications, even those written in languages beyond Python.

```
Note: In order to fully utilize the features of GraphSpace REST API, you must have an account on GraphSpace.
```

### Why use GraphSpace REST API ?

The GraphSpace REST API makes it easier than ever to use GraphSpace in new and exciting ways, such as creating external applications on top of GraphSpace. For example, 

- Create a Cytoscape plugin which will allow users to transfer networks between GraphSpace and Cytoscape. 
- Users can also automate the way they upload graphs to GraphSpace.

The scope of what can be done with the GraphSpace REST API is only limited by our imagination. Overall, if a user want a structured, extensible, and simple way to get data in and out of GraphSpace over HTTP, they should probably use the GraphSpace REST API.

### Base URL

All URLs referenced in the documentation have the following base:

> http://www.graphspace.org/api/v1/

<!---
The GraphSpace REST API is served over HTTP. In case you are 
-->



### API Reference

<iframe src="http://35.163.136.54/static/api.html" style="height: 100vh;width: 100%;"></iframe>


## GraphSpace Python Client

GraphSpace Python Client is library for the GraphSpace REST API. It simplifies the process of authentication, request construction, and response parsing for Python developers using the GraphSpace API. This clientlib is built and tested on Python 2.7.

### Installation

Install graphspace_api from PyPI using:

```
    pip install graphspace_api
```

### Usage

The library uses a client object to query against the API.

#### Add a Graph to GraphSpace

```
graphspace = GraphSpace('user1@example.com', 'user1')

# Users can change the host for the API ENDPOINTS.
# graphspace.set_api_host('localhost:8000') 

graph1 = GSGraph()
graph1.set_name('My Sample Graph')
graph1.add_node('a', popup='sample node popup text', label='A')
graph1.add_node_style('a', shape='ellipse', color='red', width=90, height=90)
graph1.add_node('b', popup='sample node popup text', label='B')
graph1.add_node_style('b', shape='ellipse', color='blue', width=40, height=40)

graph1.add_edge('a', 'b', directed=True, popup='sample edge popup')
graph1.add_edge_style('a', 'b', directed=True, edge_style='dotted')
graph1.set_data(data={
    'description': 'my sample graph'
})
graph1.set_tags(['sample'])
graphspace.post_graph(graph1)
```


#### Get a Graph from GraphSpace

```
graphspace = GraphSpace('user1@example.com', 'user1')

# Users can change the host for the API ENDPOINTS.
# graphspace.set_api_host('localhost:8000') 

graphspace.get_graph('My Sample Graph')
```

#### Make a graph publicly viewable on GraphSpace

```
graphspace = GraphSpace('user1@example.com', 'user1')

# Users can change the host for the API ENDPOINTS.
# graphspace.set_api_host('localhost:8000') 

graphspace.make_graph_public('My Sample Graph')
```

#### Make a graph privately viewable on GraphSpace

```
graphspace = GraphSpace('user1@example.com', 'user1')

# Users can change the host for the API ENDPOINTS.
# graphspace.set_api_host('localhost:8000') 

graphspace.make_graph_private('My Sample Graph')
```

#### Update a graph on GraphSpace

```
graphspace = GraphSpace('user1@example.com', 'user1')

# Users can change the host for the API ENDPOINTS.
# graphspace.set_api_host('localhost:8000') 

graph1 = GSGraph()
graph1.add_node('a', popup='sample node popup text', label='A updated')
graph1.add_node_style('a', shape='ellipse', color='green', width=90, height=90)
graph1.add_node('b', popup='sample node popup text', label='B updated')
graph1.add_node_style('b', shape='ellipse', color='yellow', width=40, height=40)

graph1.add_edge('a', 'b', directed=True, popup='sample edge popup')
graph1.add_edge_style('a', 'b', directed=True, edge_style='dotted')
graph1.set_data(data={
    'description': 'my sample graph'
})

graphspace.update_graph('My Sample Graph', graph=graph1, is_public=1)
```

#### Delete a Graph from GraphSpace

```
graphspace = GraphSpace('user1@example.com', 'user1')

# Users can change the host for the API ENDPOINTS.
# graphspace.set_api_host('localhost:8000') 

graphspace.delete_graph('My Sample Graph')
```
