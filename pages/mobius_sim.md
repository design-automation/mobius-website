---
title: Möbius SIM
---
# Möbius Spatial Information Model (SIM)

Möbius Spatial Information Model (SIM) in a Javascript/Typescript library for generating and
manipulating 3D spatial information. 

{% include fig.html 
file="mobius_sim_ent_types.png" 
caption="Möbius SIM, entity types." 
%}

{% include fig.html 
file="mobius_sim_table.png" 
caption="Möbius SIM, showing the entities that make up points, polyline, and polygons." 
%}

{% include fig.html 
file="mobius_sim_tree.png" 
caption="Möbius SIM, showing the relationship between entities for a polygon with a whole." 
%}

# SIM Conceptual Model

The SIM Conceptual Model defines how spatial information is representation. 

The conceptual model strives to be a highly generic type of representation that can be used to
represent a wide variety of types of spatial information. It has no concepts that are specific to
any type of products, such as buildings, cities, and so forth. Such concepts can be added to the
representation by the user, through user-defined collections, semantics, and connectivity

## Entities

The conceptual model defines a set of entities and attributes. 

Entities represent the geometry and topology of the spatial information. Attributes represent the
semantics of the spatial information. Attributes are key-value pairs that can eb attached to any
type of entity.

Various different types of entities are define. 
- __Model__: A the top level, there is the _model_ entity that encapsulates the whole model. 
- __Collections__: A model can contain zero or more _collections_. A collection is an aggregation
  that can contain either objects or other collections.
- __Objects__: A model can contain zero geometric entities called _objects_. Three types of objects
  are define: _polygons_, _polylines_, and _points_. 
- __Topology__: Objects have an internal topological structure made up of _topological_ entities.
  There are three types of topological entities: _wires_, _edges_, and _vertices_.
- __Positions__: A model can contain _positions_. Positions represent specific locations in the
  model, specified by an `xyz` attribute, whose value is a list of three numbers. This attribute is
  non-optional. It is the only required attribute in the SIM conceptual model. 

Overall, there are therefore 9 types of entities:
- models
- collections
- polygons, polylines, points 
- wires, edges, vertices 
- positions

## Topology

A _wire_ consists of a sequence of _edges_ and a sequence of _vertices_. Each edge connects exactly
two vertices. If a wire is closed, then the number of edges is equal to the number of vertices. If 
a wire is open, then the number of edges is one less than the number of vertices. 

Every vertex is linked to exactly one position. The `xyz` attribute of the position defines the
location of the vertex. 

Each type of object has a specific topological structure.  
- Polygons are defined by a list of closed wires. The first wire defines the outer boundary of the
  polygon. Subsequent wires define holes within the polygon.
- Polylines are defined by a single wire that can be either open or closed.
- Points are defined by a single vertex.

Topological entities are created and destroyed based on specific modelling operations. The user
cannot directly create topological entities. For example, when a user creates a polyline, the wire,
edges, and vertices will be automatically created.

## Attributes

Attributes can be added to any type of entity. An attribute has a unique name and a value. The name
is a string. The value can have the following types:
- number (float or integer)
- string
- boolean
- list, e.g. `[1,2,3]`
- dictionary, e.g. `{"a":1, "b":2, "c":3}`

The list or dictionary data structures can contain numbers, strings, booleans or other lists or
dictionaries. 

## User-defined Collections

Users can organise their spatial information in complex ways using collections. Collections can
contain heterogeneous set of objects, and can be nested to create hierarchies. This allows
representations to be defined that decompose models into different parts. In addition, objects can
be members of multiple collections, thereby allowing multiple representational schemas to be
applied at the same time. 

For example, a user creating a model of an urban neighbourhood may create collections for each
building and a collection for the roof polygons of all buildings (perhaps for solar PV potential
analysis). Each roof polygons would then be in two collections, the building and the 'roofs'.

## User-defined Semantics

Users can can define custom semantics by adding attributes to any of the entities in the model. This
allows users to customise the data representation to their particular use case. In existing spatial
representations such as GeoJSON, attributes can only be added to objects. The ability to add
attributes to the model, to collections, and to topological entities (wires, edges, and vertices) is
a powerful feature.

For example, a user creating a model of a number of buildings can create a collection for each
building and then add attributes that describe properties of the building, for instance the total
floor area. 

## User-defined Connectivity

Users can create custom connectivity relationships between objects in the model. By sharing
positions, vertices in objects can become welded. In other spatial data representations, creating
such connections is either not possible, or specific types of relationships are hard-coded into the
representation. With the SIM approach, users can define their own connectivity relationships based
on their use cases. 

For example, for certain types of network analysis, a user may want to create connectivity
relationships between polylines representing street networks. 

# SIM Programming Model

The SIM library implements the SIM COnceptual Model, and provides a Typescript API for creating and
manipulating SIM models.

The SIM API is a functional API that has functions for performing various type of modelling
operations. Entities in the model are referenced by their entity IDs. The first argument to all
functions is the SIM model that is being operated on.

For example, to create a polygon and extrude it:

```
import GIModel from ...
import pattern from ...
import make from ...
import attrib from ...
import io from ...
const model = new GIModel();
const posis = pattern.Rectangle(model, [0,0,0], [10, 20]);
const pgon = make.Polygon(model, posis);
const ext = make.Extrude(model, pgon, [0,0,10], 3, make.EExtrude.QUADS);
attrib.set(model, pgon, "type", "base", attrib.ESet.ONE_VALUE);
const data = io.Export(model, ext, io.EExport.GLTF);
```

# Source Code

Source code is available on Github.

- Lead Developer (2017 - ongoing): [Patrick Janssen](http://patrick.janssen.name)
- [Möbius SIM on Github](https://github.com/design-automation/mobius-sim){:target="blank"}

## Installation

The SIM library is available through the NPM package manager.

- [Möbius SIM on NPM](https://www.npmjs.com/package/@design-automation/mobius-sim){:target="blank"}

To install:
 - `npm i @design-automation/mobius-sim`