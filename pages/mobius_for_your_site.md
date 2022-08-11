---
title: Möbius for your site
---
# Möbius for your site

Aside from just using Mobius on its website, the models and functions can be embedded in external websites too.

## Methods for Embedding Mobius

There are two main methods to embed Mobius into an external website. The links will give more detailed instructions.

1. [Mobius Modeller.](https://github.com/design-automation/mobius-parametric-modeller-dev-0-9/blob/main/embed.md) This allows for greater customization of viewers/panels and more user interactivity, but is less lightweight.
2. [Mobius Viewer.](https://github.com/design-automation/mobius-viewer-dev-0-7/blob/main/embed.md) This is more lightweight, but has less user interactivity. Can be used when the user just needs to view the model and not edit the script. 

## Generating Mobius files
  
When embedding Mobius Viewer, a default model will likely be needed. There are two ways to create this model.

1. Create a script in Mobius Modeller and save the javascript file. This file can be saved onto dropbox, then executed in the viewer. (Mobius' website's publish function can also be used to generate embed code.)
2. Write code using [mobius-sim-funcs](https://github.com/design-automation/mobius-sim-funcs/blob/main/README.md) and [mobius-inline functions](https://github.com/design-automation/mobius-inline-funcs/blob/main/README.md) libraries. See the respective links for instructions on how to install and use the libraries, or see [Mobius Programming](https://mobius.design-automation.net/pages/mobius_programming.html) for more on the programming model. 

