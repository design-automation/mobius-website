---
title: Möbius MOOC Generator 
---
# Overview

The Möbius MOOC Generator is a Python library for streamlining the process of creating Massive Open
Online Courses (MOOCs) on the Edx platform. 

The user writes the content for the MOOCs as a series of markdown files, saved in a hierarchical
folder structure that reflects the MOOC content structure. These files can be developed
collaboratively, using existing tools such as Git version control. This makes the process of
creating and managing the MOOC content more efficient. 

The Möbius MOOC Generator library is then used to process the markdown files, and to generate a
single zip file containing all the data required to generate the whole course. This zip files can be
imported into the Edx MOOC, which will create the complete MOOC.

{% include fig.html file="mobius_mooc_generator_import.png" caption="Importing a Möbius MOOC zip
file within the Edx platform ." %}

{% include fig.html file="mobius_mooc_generator_outline.png" caption="The resulting course content,
automatically generated from the zip import." %}

## Embedding Möbius Modeller

The generator supports the ability to embed Möbius Modeller directly into the MOOC pages. This
allows learners to interact with 3D spatial models directly in the MOOC web pages.

{% include fig.html file="mobius_mooc_generator_embed.png" caption="A Möbius Modeller example
embedded directly into the MOOC web page." %}

# Links

Various links:

## Developers

- Lead PI: [Patrick Janssen](http://patrick.janssen.name)

## Source Code Repository

- [Möbius MOOC Generator Github Repository](https://github.com/design-automation/edx-generator)

## MOOCs

MOOCs created using the Möbius MOOC Generator:

- [Professional Certificate Programme in Spatial Computational Thinking](https://www.edx.org/professional-certificate/nus-spatial-computational-thinking)
- [Spatial Computational Thinking: Procedural Modelling](https://www.edx.org/course/procedural-modelling)
- [Spatial Computational Thinking: Generative Modelling](https://www.edx.org/course/generative-modelling)
- [Spatial Computational Thinking: Performative Modelling](https://www.edx.org/course/performative-modelling)
