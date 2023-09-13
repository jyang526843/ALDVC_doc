.. _gettingstarted:

==================
Getting Started
==================

Installation
----------------

To install ALDVC on your machine:

* Make sure that MATLAB (version later than 2018a) is already installed on your machine. Both Windows (later than Windows 10) and Mac OS have been tested.


* Download and unzip our code package from Mathworks File Exchange `[ALDIC Mathworks link]`_ or Github page `[ALDIC Github link]`_


* Open your MATLAB app, enter the unzipped ALDVC folder, and set it on your MATLAB working path

* Make sure these MATLAB toolboxes are installed on your computer:

    * Parallel computing toolbox

    * Wavelet

    * Imaging post-processing


.. |runbutton| image:: ./img/fig_RunButton.png
   :align: middle
   :width: 14


* ALDVC code can be initiated by opening and executing the "main_ALDVC.m" file. As shown in :numref:`img_main_ALDVC`. ALDVC code can be executed
section-by-section. Once you are familiar with the ALDVC code, you can execute the whole main file by clicking the "Run" button to run the whole file at one time ("EDITOR >> RUN >> |runbutton|"). ALDIC code is easy to modify based on user’s custom parameter choice. In this code manual, we will introduce ALDVC code section by section.



.. _img_main_ALDVC:

.. figure:: ./img/fig_main.png
   :alt: main_ALDVC.m
   :align: center
   :width: 90 %

   Main file of ALDVC code "main ALDVC.m". Each section can be executed in order by clicking "Run Section".



Volumetric Image Stack Pre-processing
----------------


To apply digital volume correlation, we need to provide at least two image stacks to compare and
register unknown deformations. These image stacks could be generated from various diagnostic
techniques, e.g., 3D confocal microscopy, X-ray tomography (CT) scans, magnetic resonance
imaging (MRI), neutron tomography, etc.


Here we assume the user has 3D image stacks for both undeformed and deformed images.
(Though your raw data sets are not in image stacks, there are lots of free software, e.g., Fiji
(https://imagej.net/Fiji), ImageJ or other image processing softwares, to export 3D image stacks.)
For example, in the subfolder "./DVC images/vol stretch tiff" there are one example of such a 3D
image stack corresponding to the "vol stretch 1001.mat" in the "ImageDownload link.txt".







References
-----------

.. _[ALDIC Mathworks link]:

2D ALDIC MATLAB code Mathworks FileExchange link. https://www.mathworks.com/matlabcentral/fileexchange/70499-augmentedlagrangian-digital-image-correlation-and-tracking.

.. _[ALDIC GitHub link]:

2D ALDIC MATLAB code Github link. https://github.com/jyang526843/2D_ALDIC.