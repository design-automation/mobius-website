---
title: Möbius Evolver
---
# Möbius Evolver

Möbius Evolver is an open-source web-app for designers to optimize 3D parametric models. The app
runs on the Amazon AWS Clouding Computing platform.

Example runs using Mobius Evolver:

- [Example 1](https://master.d3i0dy0fnq65q5.amplifyapp.com/view-searches/search-results#id=e5fbecee-ca9c-4e13-80dc-8da949424969){:target="Mobius"}
- [Example 2](https://master.d3i0dy0fnq65q5.amplifyapp.com/view-searches/search-results#id=111ade96-4e7b-4ad5-8bac-cf63dc87c89c){:target="Mobius"}

## Optimisation Algorithm

For the optimization process, an Evolutionary Programming (EP) algorithm is used. EP is one of the
four major evolutionary algorithm paradigms. It was first used by Lawrence J. Fogel in the US in
1960s as a learning process aiming to generate artificial intelligence 
([Wikipedia](https://en.wikipedia.org/wiki/Evolutionary_programming){:target="blank"}). EP focuses on
the evolution of distinct species. 

## Reflective Intelligence Amplification

Möbius Evolver supports a human-in-the-loop optimization approach. In this approach, the designer
and computer are working together as two actors, each doing what they do best. The aim is to amplify
the intelligence of the designer, through a cyclical exchange between the human and computer.

In this exchange, each actor has a specific task to perform.
- The task for the designer is to specify the design rules and design goals that will drive the
  optimization process.
- The task of the computer is to search for optimal designs, using the evolutionary algorithm.

A cyclical process emerges, where the designer and computer take turns to perform their respective
tasks. The designer will start by specifying an initial set of rules and goals. The computer will
then execute the search process, and within a few minutes, return a population of optimized designs.
The designer will then reflect on the optimized designs and will most likely see certain
deficiencies. They can then modify the rules and goals, and pass these back to the computer. The
computer will execute a new search process, thereby producing more optimized designs. This can
continue until the designer is satisfied with the results. 

## Rules and Goals

To specify the rules and goals required for a search process, the designer needs to create two types
of scripts: one or more generative scripts, and one evaluative script.

The generative script has a set of parameters, an generates design models. Varying the parameters
will vary the models that are generated,

The evaluative script analyses a 3D model can calculates an overall score based on a set of
performance criteria. These scripts can be created using Möbius Modeller. Möbius Modeller is an
open-source web application for 3D parametric modelling. The app allows users to create modelling
procedures using the Obi visual programming language. In the Obi language, you write computer
programs by drawing flowcharts and by defining procedures using 'click and fill-in-the-blanks'
coding.

Once the designer has created the scripts, they can upload them to Möbius Evolver, set a few
settings and start the search process.

## Cloud Computing

Möbius Evolver executes the evolutionary algorithm in the cloud, executing all the scripts in
parallel. This allows the search process to be massively speeded up. Evolving a 1000 design will
take just two or three minutes. This speed of execution is vital in order to keep the design process
alive. When the designer only needs to wait a few minutes to get back the optimised designs, there
is no disruption to their thought process and ideas.

# Source Code

Source code is available on Github.

- Lead Developer (2018 - ongoing): Tung Do Phuong Bui
- [Möbius Evolver on Github](https://github.com/design-automation/mobius-evo){:target="blank"}
- [Möbius Evolver Layers on Github](https://github.com/design-automation/mobius-evo-layers){:target="blank"}

## Installation

Möbius Evolver has been developed for the Amazon Web Services (AWS) cloud computing platform. 

A user-friendly installation process has been developed that makes it very easy to install Möbius
Evolver on your own AWS account. This will allow you to run your own evolutionary explorations at 
a very low cost. See the installation instructions on the 
[Möbius Evolver Github page](https://github.com/design-automation/mobius-evo){:target="blank"}.


