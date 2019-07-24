# pyLINEAR: Simulation (Demo)

## By: Russell Ryan and Kornpob Bhirombhakdi

This Notebook demonstrates how to implement pyLINEAR (the original version in IDL was described in Ryan, Casertano, & Pirzkal 2018: https://ui.adsabs.harvard.edu/abs/2018PASP..130c4501R/abstract) for simulating grism images from a direct image. In this demo, we assume that you have installed packages associated to pyLINEAR including i) polyclip, ii) h5axeconfig, and iii) pyLINEAR. You can download the packages from https://github.com/Russell-Ryan, and follow the instruction for the installation, and their documentation. After installing the packages (and other dependencies), please download the this Notebook's folder from https://drive.google.com/drive/folders/1c4er79f5tVZQG_P_zJYShGYcTYjUq-x2?usp=sharing. We recommend using Anaconda/Python3 environment for using this Notebook as well as the pyLINEAR.

In this folder, files include:

- 01_test_pylinear_simulation.ipynb = this Notebook

- img.fits = simulated direct image. This image have two gaussian sources at physical x-y pixels about (2800,2000) and (2800,1500). We will simulate a grism image associated to this direct image.

- obs.lst = information of direct images. This is a two-column text file with space delimiter. For each row, the first column specifies a direct image file, and the second column specifies its associated telescope/filter file (*.filt file included with h5axeconfig package, which can also be found in the STScI resources). In this demo, we assume the direct image img.fits was taken from HST/WFC3-F105W. If you have more than one direct images, simply add another lines.

- sed.lst = list of SED models to be simulated. This is a three-column text file with space delimiter. The first column identifies sources ID (in integer only). The second column identifies the path to the associated SED model file (which is a space-delimited text file with two columns: wavelength (in A) and flam (in erg/s/cm^2/A). This demo will generate the SED models: sed1.dat and sed2.dat. Note that we have two sources in img.fits, therefore we provide two SED models in sed.lst. The third column specifies redshift.

- wcs.lst = list of grism orientations to be simulated. This has four columns with space delimiter. The first columnn identifies the prefix (e.g., A) to the output grism image (e.g., A_flt.fits). The second to last columns identifies the orientation of the telescope, i.e., (CRVAL1, CRVAL2) and rotation.

- defaults.yml = configuration file of pyLINEAR.

Unlike the other files provided in this folder, defaults.yml must be copied (or edited) manually to the local library of pyLINEAR, e.g., '/Users/kbhirombhakdi/anaconda2/envs/py3/lib/python3.7/site-packages/pylinear-1.0-py3.7.egg/pylinear/config/defaults.yml'. Please see ??? for details about the configuration file. Note that, as specified in the configuration file, we will simulate grism images from HST/WFC3-IR-G102 using the HST/WFC3-F105W direct image (img.fits). We will do only simulation, so make sure setting 'perform: true' and 'gzip: false' in the simuation section, and 'perform: false' in both extraction and cutout sections.

To start this demo, run this Notebook from its root.
