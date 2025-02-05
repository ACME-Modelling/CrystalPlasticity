# Introduction (Crystal Plasticity for Representative Volume Elements)

The purpose of the following repository is to facillitate the development of crystal plasticity finite element models. These models are developed for the prediction of complex material behaviours, such as crack propagation, creep, fatigue, tensile, etc. The following README was last updated on the 6th of June, 2023.

# Dependencies

The following section details the requirements to run the script.

## Python Packages

The scripts also require several Python packages. To install these packages, `pip` is required. If you do not have `pip` installed, please following [these instructions](https://linuxize.com/post/how-to-install-pip-on-ubuntu-18.04/).

* Numpy (`python3.9 -m pip install numpy`).

## Repository Structure

The following diagram shows the high level structure of the repository. 

```
cp_rve/
├── __common__/
├── tessellator/
├── mesher/
└── simulator/
```

## Common Directory

The `__common__` directory (`cp_rve/__common__/`) contains common helper code used in the programs in the repository. Each program is contained within their own directory with a `main.py` file. Once the user has moved into the directory (via `cd`), they can make function calls in `main.py` using the provided `API` class, and run the program via `python3 main.py`.

## Tessellator

The `tessellator` directory (`cp_rve/tessellator/`) contains code for developing tessellations of cubic microstructures using [Neper](https://github.com/neperfepx/neper).

## Mesher

The `mesher` directory (`cp_rve/mesher/`) contains code for creating adaptive hexahedral meshes of microstructures using [Cubit Coreform](https://coreform.com/products/coreform-cubit/). The program has the feature of exporting the crystallographic orientations of the individual grains.

## Simulator

The `simulator` directory (`cp_rve/simulator/`) contains code for running [MOOSE](https://github.com/idaholab/moose) simulations. The code currently only runs a model that couples the crystal plasticity constitutive equations with the ShamNeedleman grain boundary equation to predict creep deformation.
