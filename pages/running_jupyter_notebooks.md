---
title: Running Jupyter Notebooks Locally
sidebar: mydoc_sidebar
permalink: running_jupyter_notebooks.html
---

# Overview

We will provide waterhackweek participants with a centralized, cloud-based environment for working on projects and tutorials. More details on this will follow. For those of you interested in working with our material on your local machine, the steps for this are provided below.

# Acquire the tutorials

To get a copy of the tutorial contents on your local machine, clone the [github repository](https://github.com/waterhackweek/tutorial_contents).

```bash
$ git clone https://github.com/waterhackweek/tutorial_contents.git
```

This repo will contain all of the materials for WaterhackWeek 2018. In order for us to run the notebooks within each tutorial, we need to run Jupyter Notebook.

## Installing Jupyter Notebooks

The first step in installing a Jupyter Notebook is to install conda. More information on conda can be found in our introductory tutorial [here](https://waterhackweek.github.io/preliminary/01-conda-tutorial/).

1. Jupyter notebooks can be easily installed within a conda environment. To do this, go ahead and open up your terminal and run the command below. This will install jupyter notebooks and their dependencies.

    ```bash
    $ conda install -c conda-forge jupyter
    ```

2. Once `jupyter` is installed, you can run `jupyter notebook` and a jupyter notebook should open up on your default browser. If not, you can go back to your terminal and copy the url.

    ```bash
    Copy/paste this URL into your browser when you connect for the first time,
        to login with a token:
           http://localhost:8888/?token=dd82f1e1d85a38d5b0d65768420274e25c8fd11c7a9a6626
    ```

    **Note**:
    - The default python `environment/kernel` for the jupyter notebook is the conda environment where you ran the `jupyter notebook` command. In the example above, this is the root.
    - The directory where you ran `jupyter notebook` is the root directory of the jupyter notebook.

3. To shutdown the jupyter notebook, make sure that you save your notebooks by using `command + s` or `ctrl + s`, then go back to your terminal and doing `ctrl + c`.

## Installing `nb_conda_kernels` for changing among conda environments.

You will only need to install `nb_conda_kernels` once within your root conda environment, since you will be able to switch between conda environments afterwards within the notebook. Open up your terminal and make sure that you are on the root conda environment by typing `conda env list`; the activated environment is starred `*`.

Run the command below to install the packages.
```bash
$ conda install -c conda-forge ipykernel nb_conda_kernels
```
**Note: For `nb_conda_kernels` to see your other conda environments, you need to install `ipykernel` in those conda environment.**


## Installing a general waterhack vector and raster conda environment

Go to the `tutorial_contents` folder and run the command below.

```bash
$ conda env create -f ghw_environment.yml
```

This will install a conda environment named `waterhackenv`. You can use this environment for your vector and raster geospatial work.

If you would like to install the conda environment for each tutorial separately, you can go into the tutorial's subfolder and create the environment from `environment.yml` file.