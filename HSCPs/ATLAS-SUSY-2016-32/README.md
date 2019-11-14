# HSCP Recasting #

## Authors: ##
[Andre Lessa](mailto:andre.lessa@ufabc.edu.br)

This repository holds the main code for recasting the 13 TeV ATLAS heavy stable charged particle
search ([ATLAS-SUSY-2016-32](http://atlas.web.cern.ch/Atlas/GROUPS/PHYSICS/PAPERS/SUSY-2016-32/))
based on the recasting details and code provided [here](http://atlas.web.cern.ch/Atlas/GROUPS/PHYSICS/PAPERS/SUSY-2016-32/hepdata_info.pdf)

## Pre-Requisites ##

The following pre-requisites must be installed before compiling the main code:

  * [Pythia8](http://home.thep.lu.se/~torbjorn/pythia8/) (with ROOT bindings)

## Installation/Compiling ##

In order to compile the recasting code, run:

```
make main_hscp.exe pythia8path=<PATH-TO-PYTHIA8FOLDER>
```

where PATH-TO-PYTHIA8FOLDER should point to the Pythia8 folder containing the Pythia lib and include folders.

## Running ##

Instructions for running the main code can be obtained running:

```
./main_hscp.exe -h
```

The basic required input is a (parton level) LHE or SLHA file.
For instance, running:

```
./main_hscp.exe -f example.slha -n 100 -o example.lhe
```

should generate 100 events and display the efficiencies for the given input file.
A simplified LHE output file (example.lhe) is also generated with the isolated HSCPs, their momentum,
the efficiency for each particle and the final efficiency.
This information can then be used later to rescale the efficiencies according to the HSCP lifetime.

## Validation ##

The validation of the signal efficiencies (efficiency times acceptance)
for direct production of staus can be found in the [validation folder](validation).
The output (.lhe files) was generated using the SLHA files and pythia8.cfg file stored in the folder.
The following validation plot can be generated running this [ipython notebook](validation/validation.ipynb):


![Alt text](validation/validationPlot.png?raw=true "Validation Plot")