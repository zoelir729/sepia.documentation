.. SEPIA documentation master file, created by
   sphinx-quickstart on Sat May 25 22:48:00 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

SEPIA Documentation
===================

Welcome to the SEPIA documentation! Here you can find all the documents related to SEPIA.

**SEPIA** provides a graphical user interface (GUI) in Matlab to build data processing pipelines related to quantitative susceptibility mapping (QSM).

**SEPIA** is designed to solve two issues we encountered in QSM:  

1. Using algorithms from toolboxes developed by different research groups,
2. Having a platform such that we can quickly adjust (and remember) parameters of each algorithm.  

The purpose of SEPIA is to provide a platform for easy access to different QSM processing methods in the field. It provides interfaces to use the following three toolboxes freely available online for academic purposes, i.e.  

1. `MEDI toolbox <http://pre.weill.cornell.edu/mri/pages/qsm.html>`_  
2. `STI Suite <https://people.eecs.berkeley.edu/%7Echunlei.liu/software.html>`_  
3. `FANSI toolbox <https://gitlab.com/cmilovic/FANSI-toolbox>`_  
4. `SEGUE <https://xip.uclb.com/i/software/SEGUE.html>`_

Through SEPIA we hope researchers who are not coming from the field could also be able to use QSM for their research. For those more experienced researchers, we also hope this tool can simplify your workflow.

Table of Contents
=================

.. toctree::
   :maxdepth: 1
   :caption: Getting started
   :name: sec-getstart

   getting_started/Installation
   getting_started/Data-preparation
   getting_started/Sepia-header
   getting_started/Sepia-output
   getting_started/Release-note

.. toctree::
   :maxdepth: 1
   :caption: Graphical User Interface (GUI)
   :name: sec-gui

   gui/Sepia-One-stop-QSM-processing
   gui/Phase-unwrapping-standalone
   gui/Background-field-removal-standalone
   gui/QSM-standalone

.. toctree::
   :maxdepth: 1
   :caption: Supported algorithms in SEPIA
   :name: sec-method

   method/Phase-unwrapping-algorithms
   method/Background-field-removal-algorithms
   method/QSM-algorithms
   method/Lookup-table-algorParam

.. toctree::
   :maxdepth: 1
   :caption: Demonstration
   :name: sec-demo

   demo/Choosing-a-right-phase-unwrapping-method-for-your-data

.. toctree::
   :maxdepth: 1
   :caption: Tutorial
   :name: sec-tutorial

   tutorial/SEPIA101/index
   tutorial/integration_new_method/part_1/index
   tutorial/integration_new_method/part_2/index
   tutorial/fMRItoolkit2019/index

.. toctree::
   :maxdepth: 1
   :caption: Acknowledgements and References
   :name: sec-acknowledge

   pages/Acknowledgements
   pages/References



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
