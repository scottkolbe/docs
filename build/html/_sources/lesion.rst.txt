Lesion Segmentation Tool (LST)
==============================

For many pathological MRI applications it is necessary to segment out T2 hyperintense
lesions from FLAIR scans. `LST <https://www.applied-statistics.de/lst.html#LST_about>`_ 
provides algorithms to do this automatically. LST is based on 
SPM12 and has two alorithms LGA (lesion growth algorithm) and LPA (lesion prediction algorithm). 
LGA requires a T1 and FLAIR scan. LPA is newer and requires only a FLAIR scan. This 
paper looks at both in the context of MS lesion segmentation:

Egger et al. (2017). MRI FLAIR lesion segmentation in multiple sclerosis: Does automated segmentation hold up with manual annotation? NeuroImage. Clinical, 13, 264–270. http://doi.org/10.1016/j.nicl.2016.11.020

LST requires `SPM12 <https://www.fil.ion.ucl.ac.uk/spm/software/spm12/>`_ within MATLAB. Please 
see download and install instructions on the relevant websites.

LST has comprehensive documentation here: 
https://www.applied-statistics.de/LST_documentation.pdf

