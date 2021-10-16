---
title: Möbius Spatial Information Model (SIM)
---
# Overview

 Möbius Spatial Information Model in a Javascript/Typescript library for generating and manipulating
 3D models. 

- This pages needs to be updated (16 Oct 2021)

## Conceptual Model

In order to write code using the Spatial Information Model (SIM) library, it is useful to
understand the SIM conceptual model.

### Topological Modelling

In order to allow for greater control, the SIM approach requires models to be defined using a
topological modelling approach. Topology is a mathematical approach that defines components in terms
of adjacency and connectivity. For example, a mesh may be described as being an object with a set of
*faces*, each bounded by a set of straight *edges*, each defined by a pair of *vertices*, each of
which is associated with a point in space.

Topology is useful in that it allows models to be described and analysed in more advanced ways. For
example, in the case of the mesh, the faces adjacent to any particular face can be easily discovered
by navigating through the topological data structure. However, the downside of topology is that it
makes models heavier, due to the fact that additional data needs to be stored. 

In order to ensure that models remain lightweight and easy to work with, the PIM approach defines
topology implicitly. This means that geometric objects can stored using simple lightweight
representations, and topology is generated on demand only when needed, in response to certain user
operations.

### Model Entities

Elements in the model consist of three types: geometric objects, geometric points, and implicit
topological components.

- __Objects__ are any type of geometric object, such as polylines and polymeshes. 
- __Points__ are 3D points in the model, defined by a set of XYZ coordinates. 
- __Topology__ consists of a set of implicit component parts belonging to individual objects.

Objects are defined through points. For example, a polyline is defined by connecting a series of
points. Topological components then form a data structure that creates a well defined relationship
between the objects and the points.

### Model Semantics

Semantics can be added to the model in two ways: by defining attributes and by defining groups.

- __Attributes__ are data values that can be attached to elements in the model. Attributes can be
  attached to all element types, including geometric objects, geometric points, and topological
  components. Attributes allow elements in the model to have different values. For example, creating
  an attributed called "colour" for *faces*, means that all faces in the model can be assigned a
  different colour.

- __Groups__ are collections of elements in the model. All elements types can be grouped, including
  geometric objects, geometric points, and topological components. Each group can be assigned a set
  of properties, as key value pairs. Groups can also be nested, thereby allowing various more
  complex types of data structures to be created, including hierarchies.

The use of attributes and groups allows rich 3D data sets to be created by users, suited and
customised to their specific purposes.

## Installation

The SIM library is available through the NPM package manager.

- [Möbius SIM on NPM](https://www.npmjs.com/package/@design-automation/mobius-sim){:target="blank"}

To install:
 - `npm i @design-automation/mobius-sim`

## Source Code

Source code is available on Github.

- [Möbius SIM on Github](https://github.com/design-automation/mobius-sim){:target="blank"}

