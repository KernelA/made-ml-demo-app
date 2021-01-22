# 3D classification primitive with PyTorch Geometric

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/KernelA/made-ml-demo-app.git/master?urlpath=%2Fvoila%2Frender%2Fdemo.ipynb)

## Description

This project demonstrates application of [PyTorch Geometric](https://github.com/rusty1s/pytorch_geometric) and other technologies for creating a simple demo app.

[Repository with model here](https://github.com/KernelA/made-ml-demo-app-model)

Used technologies:
* [Voila for creating web-application](https://github.com/voila-dashboards/voila)
* [Jupyter Widgets for GUI](https://jupyter.org/widgets)
* [BinderHub for running](https://github.com/jupyterhub/binderhub)

Voila theme used [from other repository](https://github.com/voila-dashboards/voila-material)

## Requirements

1. Python 3.7 or higher.
2. Anaconda or Miniconda.
3. Git LFS (weights for model is storing in LFS).

## How to tun

Create anaconda environment:
```
conda env create -n 3d-cls-demo --file ./environment.yml
conda activate 3d-cls-demo
```

For running in Voila:
```
python ./setup.py develop
```

Files from directory `share` must be in right place, otherwise will be error when Voila starting. For Anaconda:
```
jupyter --paths
```

Possible output for Windows:
```
data:
    D:\...\3d-cls-demo\share\jupyter
```

Directory structure in ` D:\...\3d-cls-demo\share\jupyter` must be:
```
├───nbconvert
│   └───templates
│       ├───asciidoc
│       ├───base
│       ├───basic
│       ├───classic
│       │   └───static
│       ├───compatibility
│       ├───html
│       ├───lab
│       │   └───static
│       ├───latex
│       ├───markdown
│       ├───material
│       │   └───static
│       ├───python
│       ├───reveal
│       │   └───static
│       ├───rst
│       └───script
└───voila
    └───templates
        ├───base
        │   └───static
        ├───classic
        │   └───static
        ├───lab
        └───material
            └───templates
```

Note `material` name. This is directory with settings of theme for Voila application. Corresponding directories must be copy manually. Some problems were with `setup.py` under Windows.

After you need to invoke command:
```
voila ./demo.ipynb --template material
```

