Data conversion for MRI analysis
================================

Most MRI analysis applications do not work well with DICOM data so it is generally necessary 
to convert your data to a friendlier format such as nifti (.nii) or MRtrix format (.mif). 
Depending on what you are doing there are several ways to do this. 

Large scale conversion to nifti
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you have large amounts of DICOM data and want to convert it all in bulk to nifti I 
recommend using MRIConvert. This is a small gui program that can be downloaded for free 
or is available on MASSIVE using the following commands in the terminal:

.. code-block:: bash

   $ module load mriconvert/2.0.1
   $ MRIConvert

MRIConvert is useful because it uses DICOM header information to sort the files and name them 
with header data that can then be used to automate analysis protocols. For example, you can 
put the protocol name and study data in the file name to then use BASH commands to search 
and analyse data.

Single image conversion with MRtrix
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

MRtrix, although primarily a diffusion MRI package, has a very flexible data conversion tool that is 
available on MASSIVE: 

.. code-block:: bash

   $ module load mrtrix/3XXXX
   $ mrconvert $DICOM_INPUT $OUTPUT

mrconvert has some very flexible features such as intuitive reordering or reshaping of 
image matrix dimensions, and flexible output formats including NII and their own MIF format.

Diffusion MRI conversion
^^^^^^^^^^^^^^^^^^^^^^^^

Diffusion MRI requires some additional thought when converting because the diffusion gradient 
vectors and b-values must also be extracted from the DICOM header. `MRCONVERT 
<https://mrtrix.readthedocs.io/en/latest/reference/commands/mrconvert.html>`_ from MRtrix 
does this seamlessly:

.. code-block:: bash

   $ module load mrtrix/3XXXX
   $ mrconvert $DICOM_INPUT $MIF_OUTPUT

The MRtrix MIF format stores the gradient directions and b-values, and also stores commands 
used when manipulating the data so you can easily see what has been done to the data. 

Converting compressed DICOM
^^^^^^^^^^^^^^^^^^^^^^^^^^^

DICOM supports JPEG compression for image storage but most conversion tools can't handle 
JPEG DICOM natively. A workaround is to first decompress the DICOM files using `DCKTK 
<https://dicom.offis.de/dcmtk.php.en>`_. Follow the online instructions for installing DCMTK 
then use the following command to decompress the data:

.. code-block:: bash

   $ for img in compressed_dcmdir/*; do dcmdjpeg compressed_dcmdir/$img decompressed_dcmdir/$img; done

You should then be able to convert the decompressed data.
