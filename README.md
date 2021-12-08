# ERCA
http://erca-school.eu/

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/mickaellalande/ERCA/main)

We will download the Copernicus ERA5 reanalysis data from the European Centre for Medium-Range Weather Forecasts (ECMWF) and analyze the Earth's near-surface temperature from 1979 to the present. For this we will use several classic Python packages:
- [xarray](http://xarray.pydata.org/en/stable/): is an open source project and Python package that makes working with labelled multi-dimensional arrays simple, efficient, and fun! ([Xarray Tutorial](https://xarray-contrib.github.io/xarray-tutorial/) / [Xarray | SciPy 2020](https://www.youtube.com/watch?v=mecN-Ph_-78&list=PLYx7XA2nY5Gde-6QO98KUJ9iL_WW4rgYf&index=4))
- [dask](https://dask.org/): provides advanced parallelism for analytics ([jacobtomlinson/dask-video-tutorial-2020](https://github.com/jacobtomlinson/dask-video-tutorial-2020) / [Dask | SciPy 2020](https://www.youtube.com/watch?v=EybGGLbLipI&list=PLYx7XA2nY5Gde-6QO98KUJ9iL_WW4rgYf&index=6))
- [jupyter](https://jupyter.org/): for using jupyter-notebook / lab
- [matplotlib](https://matplotlib.org/): back-end for making plots
- [cartopy](https://scitools.org.uk/cartopy/docs/latest/): replace basemap, back-end for map projections
- [proplot](https://proplot.readthedocs.io/en/stable/): a lightweight matplotlib wrapper for making beautiful, publication-quality graphics (still in development)
- [xesmf](https://xesmf.readthedocs.io/en/latest/): Universal Regridder for Geospatial Data (only for Linux and Mac, an alternative is the [interp](http://xarray.pydata.org/en/stable/interpolation.html#example) function from xarray)
- [intake-esm](https://intake-esm.readthedocs.io/en/stable/): an intake plugin for parsing an Earth System Model (ESM) catalog and loading assets into xarray datasets

Note that we will be working with an already pre-installed environment with [binder](https://mybinder.org/) (which will not be saved so remember to download the notebooks at the end of the session if you want to keep track of them). If you want to install the same environment on your machine, you can do it directly by typing the command `conda env create -f environment.yml` using the environment file `environment.yml` from this reposiroty (only functional under Linux, otherwise you can remove the `xesmf` package from the file for Windows). You need to have [Anaconda](https://www.anaconda.com/products/individual) or [Minconda](https://docs.conda.io/en/latest/miniconda.html) already pre-installed on your machine. For that I advise you my article on the subject (steps 2, 3 and 4; the rest being to install it on a server — to adapt for non Linux machines): https://mickaellalande.github.io/post/tutorial/how-to-install-jupyter-notebook-on-a-server/ and then to manage your conda environments always come back to the official doc: https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file.

The versions of the packages used can also be found in the `environment.yml` file. Note that these are not the latest versions. Be careful if you upgrade, because there are often conflicts between some packages and the latest versions of some other packages or python itself (e.g., version 0.6.4 of proplot does not work with version 3.3 of matplotlib, or cartopy still does not work with the latest version 3.9 of python... what might already have evolved at the time of this session). Be particularly careful with Proplot which is a package under development and which evolves very quickly, including changes of syntax, thus refer to the version 0.6.4 for these practical works: https://proplot.readthedocs.io/en/v0.6.4/.

Some issues related with this environment:
- xESFM installation: https://github.com/JiaweiZhuang/xESMF/issues/47
- xESFM NaN's: https://github.com/JiaweiZhuang/xESMF/issues/15
- Proplot colormaps: https://github.com/lukelbd/proplot/issues/123
- Proplot colorbar: https://github.com/lukelbd/proplot/issues/124


## Getting started with xarray

Before we start and get to the heart of the matter, we will beging with a simple example notebook to get to know `xarray`. Click on the Binder button at the top of this README to start a session in a virtual online environment (or launch it on your personnal machine if you installed the environment), then open the notebook: `01_xarray_get_started.ipynb`.

## Exploring ERA5 data

Now that we've got the hang of xarray, let's apply it to real data! Open the notebook `02_ERA5.ipynb` and follow the instructions.

- download
- plot clim
- spatial trends
- global time series (show Arctic Amplification)
- select an area around your country and compare to the global average
- share it on a whiteboard!

## Comparison with CMIP6 models

https://github.com/mickaellalande/intake_CMIP6/blob/main/README.md
https://github.com/mickaellalande/MC-Toolkit/tree/master/intake
https://intake-esm.readthedocs.io/en/stable/

- select one model from your country
- compare to ERA5
- show future projections 
- share again on a whiteboard the results on your country

## Show Dask parallel (if time)
- in local show open_mfdataset
- and parallel mean for example
- give links for more 

/!\ Pensez à faire un clear outputs avant de mettre la chose en ligne ! (ou alors créer une branch solution) /!\


