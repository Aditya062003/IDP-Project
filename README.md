# The DEM's of the Moon

This repository explains how to make a geologic map of the moon using open-source data from the [USGS](https://www.usgs.gov/centers/astrogeo-sc/data-tools), [IAU](https://planetarynames.wr.usgs.gov/), and [NASA](https://solarsystem.nasa.gov/) and [Zenodo](https://zenodo.org/records/1133969). Software used includes `Python 3.7.1`.

### Dependencies

- [Python](https://www.python.org/) version 2.7 or 3.5+
- [Cartopy](http://scitools.org.uk/cartopy/) >= 0.14.2.  Cartopy itself has a
number of [dependencies](http://scitools.org.uk/cartopy/docs/latest/installing.html#installing),
including the GEOS and Proj.4.x libraries.  (For Ubuntu systems, these can be
installed through the `libgeos++-dev` and `libproj-dev` packages,
respectively.)
- [h5py](http://www.h5py.org/) >= 2.6.0
- [Keras](https://keras.io/) 1.2.2 [(documentation)](https://faroit.github.io/keras-docs/1.2.2/);
  also tested with Keras >= 2.0.2
- [Numpy](http://www.numpy.org/) >= 1.12
- [OpenCV](https://pypi.python.org/pypi/opencv-python) >= 3.2.0.6
- [*pandas*](https://pandas.pydata.org/) >= 0.19.1
- [Pillow](https://python-pillow.org/) >= 3.1.2
- [PyTables](http://www.pytables.org/) >=3.4.2
- [TensorFlow](https://www.tensorflow.org/) 0.10.0rc0, also tested with
  TensorFlow >= 1.0

This list can also be found in the `requirements.txt`.

#### Crater Catalogues

For the ground truth longitude / latitude locations and sizes of craters, we
combine the [LROC Craters 5 to 20 km diameter][lroc cat] dataset with the
[Head et al. 2010 >= 20 km diameter][head cat] one ([alternate download
link][head cat2]).  The LROC dataset was converted from ESRI shapefile to .csv.
They can be found under the `catalogues` folder of the repo, and have had their
formatting slightly modified to be read into *pandas*.

During initial testing, we also used the [Salamunićcar LU78287GT
catalogue][sala cat].

### How to Run?

Each stage has a corresponding script: `run_input_data_gen.py` for
generating input data, `run_model_train.py` to build and train the convnet, 
and `run_get_unique_craters.py` to validate predictions and generate a crater
atlas.  User-defined parameters, and instructions on on how to use each script,
can be found in the scripts themselves.

### Quick Usage

See `final-ver.ipynb` for basic examples on generating sample
datasets, loading a pre-trained CNN and using it to make predictions on
samples.

### Sample Predictions

![CNN1](final-evaluation/CNN1.png?raw=true)
![CNN2](final-evaluation/sample-predictions/sample-1.png?raw=true)
![CNN3](final-evaluation/sample-predictions/sample-2.png?raw=true)

### Model Summary
![model_summary](https://github.com/Aditya062003/IDP-Project/assets/102402625/fc7bd9cd-8423-4417-80b1-36a1211a37c0)
