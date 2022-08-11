---
title: Möbius Programming
---
# SIM Programming Model - Typescript/Javascript

The SIM library implements the [SIM Conceptual Model](https://mobius.design-automation.net/pages/mobius_sim.html), and provides a Typescript API for creating and manipulating SIM models.

The SIM API is a functional API that has functions for performing various type of modelling
operations. Entities in the model are referenced by their entity IDs. The first argument to all
functions is the SIM model that is being operated on.

For example, to create a polygon and extrude it:

```
import * as Funcs from '@design-automation/mobius-sim-funcs'

const sf = new Funcs.SIMFuncs();

const inl_example = sf.inl.XY;

const posis = sf.pattern.Rectangle([0,0,0],5);
const pgon = sf.make.Polygon(posis);
const ext = sf.make.Extrude(pgon, [0,0,10], 3, make.EExtrude.QUADS);
sf.attrib.set( pgon, "type", "base", attrib.ESet.ONE_VALUE);
const data = sf.io.Export(ext, io.EExport.GLTF);

```

See [Möbius for your site](https://mobius.design-automation.net/pages/mobius_for_your_site.html) for how to integrate the generated models onto your own websites.

# SIM Python

A Python library for reading and writing Mobius SIM files.

See [gen_model.py](https://github.com/design-automation/mobius-sim-py/blob/main/examples/gen_model.py) for examples of usage.

# Source Code

Source code is available on Github.

- Lead Developer (2017 - ongoing): [Patrick Janssen](http://patrick.janssen.name)
- [Möbius SIM on Github](https://github.com/design-automation/mobius-sim){:target="blank"}

- [Möbius SIM Functions on Github](https://github.com/design-automation/mobius-sim-funcs){:target="blank"}
- [Möbius SIM Inline Functions on Github](https://github.com/design-automation/mobius-inline-funcs){:target="blank"}

- [Möbius SIM Python on Github](https://github.com/design-automation/mobius-sim-py){:target="blank"}

## Installation

The SIM library is available through the NPM package manager.

- [Möbius SIM on NPM](https://www.npmjs.com/package/@design-automation/mobius-sim){:target="blank"}
- [Möbius SIM Functions on NPM](https://www.npmjs.com/package/@design-automation/mobius-sim-funcs){:target="blank"}

To install:
 - `npm i @design-automation/mobius-sim`

