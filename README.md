# ERCA
http://erca-school.eu/

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/mickaellalande/ERCA/main)

We will download the Copernicus ERA5 reanalysis data from the European Centre for Medium-Range Weather Forecasts (ECMWF) and analyze the Earth's near-surface temperature from 1979 to the present. For this we will use several classic Python packages:
- [xarray](http://xarray.pydata.org/en/stable/): is an open-source project and Python package that makes working with labelled multi-dimensional arrays simple, efficient, and fun! ([Xarray Tutorial](https://xarray-contrib.github.io/xarray-tutorial/) / [Xarray | SciPy 2020](https://www.youtube.com/watch?v=mecN-Ph_-78&list=PLYx7XA2nY5Gde-6QO98KUJ9iL_WW4rgYf&index=4))
- [dask](https://dask.org/): provides advanced parallelism for analytics ([jacobtomlinson/dask-video-tutorial-2020](https://github.com/jacobtomlinson/dask-video-tutorial-2020) / [Dask | SciPy 2020](https://www.youtube.com/watch?v=EybGGLbLipI&list=PLYx7XA2nY5Gde-6QO98KUJ9iL_WW4rgYf&index=6))
- [jupyter](https://jupyter.org/): for using jupyter-notebook / lab
- [matplotlib](https://matplotlib.org/): back-end for making plots
- [cartopy](https://scitools.org.uk/cartopy/docs/latest/): replace basemap, back-end for map projections
- [proplot](https://proplot.readthedocs.io/en/stable/): a lightweight matplotlib wrapper for making beautiful, publication-quality graphics (still in development)
- [xesmf](https://xesmf.readthedocs.io/en/latest/): Universal Regridder for Geospatial Data (only for Linux and Mac, an alternative is the [interp](http://xarray.pydata.org/en/stable/interpolation.html#example) function from xarray)
- [intake-esm](https://intake-esm.readthedocs.io/en/stable/): an intake plugin for parsing an Earth System Model (ESM) catalog and loading assets into xarray datasets

Check the **Environment** section at the end of this README if you want to know more about the environment and/or to install it on your local machine.

## Getting started with xarray

Before we start and get to the heart of the matter, we will begin with a simple example notebook to get to know `xarray`. Click on the Binder button to start a session (or launch it on your personal machine if you installed the environment), then open the notebook: `01_xarray_get_started.ipynb`.

- Load an example dataset
- Plot with xarray
- Select data / Make mask
- Resample / Groupby
- Computation (climatology, seasons, etc.)
- Weighted average
- Make projected plots (cartopy / proplot)
- Check versions

## Exploring ERA5 data

Now that we've got the hang of xarray, let's apply it to real data! Open the notebook `02_ERA5.ipynb` and follow the instructions.

- Download ERA5 / Read file
- Check size / Make chunks
- Compute and plot climatology
- Seasonal and regional plots
- Compute trends

## ERA5 comparison with CMIP6 models

In this part, we will compare ERA5 to CMIP6 model outputs: `03_intake_CMIP6.ipynb`

- Get CMIP6 model with `intake-esm`
- Visualize data
- Compare to ERA5 (regrid)
- Plot global bias
- Plot time series with projections

## Show Dask parallel (if time)
- in local show open_mfdataset
- and parallel mean for example
- give links for more 

/!\ Pensez à faire un clear outputs avant de mettre la chose en ligne ! (ou alors créer une branch solution) /!\


## Environment

Note that we will be working with an already pre-installed environment with [binder](https://mybinder.org/). If you want to install the same environment on your machine, you can do it directly by typing the command `conda env create -f environment.yml` using the environment file `environment.yml` from this repository (only functional under Linux, otherwise you can remove the `xesmf` package from the file for Windows). You need to have [Anaconda](https://www.anaconda.com/products/individual) or [Minconda](https://docs.conda.io/en/latest/miniconda.html) already pre-installed on your machine. If not, for Linux users, you can check this (steps 2, 3, and 4; the rest is to install it on a server — to adapt for non-Linux machines): https://mickaellalande.github.io/post/tutorial/how-to-install-jupyter-notebook-on-a-server/. For managing your conda environments always come back to the official documentation: https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file.

The package versions can be found in the `environment.yml` file. Be careful if you want to upgrade this environment, because there are often conflicts between some packages (e.g., version 0.6.4 of proplot does not work with version 3.3 of matplotlib, or cartopy does not work with the latest version 3.9 of python... but this can have already evolved at the time of this session). Be particularly careful with Proplot which is a package under development and which evolves very quickly, including changes of syntax, thus refer to version 0.6.4 for these practical works: https://proplot.readthedocs.io/en/v0.6.4/.

Some issues related with this environment:
- xESFM installation: https://github.com/JiaweiZhuang/xESMF/issues/47
- xESFM NaN's: https://github.com/JiaweiZhuang/xESMF/issues/15
- Proplot colormaps: https://github.com/lukelbd/proplot/issues/123
- Proplot colorbar: https://github.com/lukelbd/proplot/issues/124


