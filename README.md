# The DEM's of the Moon

This repository explains how to make a geologic map of the moon using open-source data from the [USGS](https://www.usgs.gov/centers/astrogeo-sc/data-tools), [IAU](https://planetarynames.wr.usgs.gov/), and [NASA](https://solarsystem.nasa.gov/). Software used includes `Python 3.7.1`.

**Python dependencies:** `pandas` `cartopy` `matplotlib` `os` `numpy` `shapefile` `jupyter`.

## Table of Contents

1. [Gathering and processing data](#data)
2. [Map design in Python](#python)

**Changing the Map Projection of a DEM File:** The original DEM data file uses a Plate Carrée projection, so I used the command line installation of `GDAL` to transform the map into Eckert IV and Orthographic projections.
