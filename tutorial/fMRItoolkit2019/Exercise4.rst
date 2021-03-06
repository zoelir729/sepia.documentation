.. _fmritoolkit2019-exercise4:

Exercise 4
==========

Objectives
----------

- Understanding QSM dipole inversion
- Gaining experience to use QSM algorithms

Data Required
^^^^^^^^^^^^^

- a 3D local field image (*Sepia_peel-4_local-field.nii.gz* in the previous exercise output directory)
- a 3D refined brain mask (*Sepia_peel-4_mask-qsm.nii.gz* in the previous exercise output directory)
- a SEPIA header (*Sepia_header.mat* in the input directory)

Estimated time
^^^^^^^^^^^^^^

About 15 min.

The Last Step
-------------

The last step of QSM processing is to deconvolute the local (tissue) field by the unit dipole field, such that the tissue magnetic susceptibility can be revealed. This can be described by:

.. math::
   \chi = F^{-1}[\frac{F(Tissue field)}{F(d)}]
   :label: di

where :math:`F` and :math:`F^{-1}` are the Fourier and inverse Fourier transform operators.

This is the so-called dipole inversion of QSM, which is just the element-wise division between the Fourier transforms of the two images.

.. toctree::
   :maxdepth: 1

   Theory_dipoleinversion

Sounds simple, isn't it? Let's try it out!

QSM: Dipole inversion
---------------------
Move to the **QSM** tab of SEPIA. 

Exercise 4.1
^^^^^^^^^^^^
**I/O** panel:

1. Select the **Local field** input: *Sepia_peel-4_local-field.nii.gz* (from the previous exercise output directory), 

2. Select the **Header**: *Sepia_header.mat*,

3. Change the **Output basename** of the output to: *~/qsm_tutorial/data/output_qsm/Sepia_tkd-0*,

4. Select the **Brain mask**: *Sepia_peel-4_mask-qsm.nii.gz* (from the previous exercise output directory). 

   .. note:: An updated brain mask has to be used here because some edges were excluded from the original brain mask in the last operation.

   .. image:: images/qsm_tab_io.png

**QSM** panel:

5. To do exactly the operation as in Eq. :eq:`di`, set the threshold of the **TKD** algorithm to '0' and press **Start**.

   .. image:: images/qsm_tab_algorithm.png

6. Check the result *Sepia_tkd-0_QSM.nii.gz* in the output directory. Set the display window to 'Min. -0.2' and 'Max. 0.2' (ppm). Does it look like the QSM map as we expected?

.. toctree::
   :maxdepth: 1

   Exercise4_answer1

Exercise 4.2
^^^^^^^^^^^^

To avoid the previous QSM map we can increase the threshold of the **TKD**. 

#. Change the **Output basename** to: *~/qsm_tutorial/data/output_qsm/Sepia_tkd-0p15*. 

#. Change the threshold of the **TKD** algorithm to 0.15 and press **Start**.

#. Check the result *Sepia_tkd-0p15_QSM.nii.gz* in the output directory. Display it along with the *Sepia_tkd-0_QSM.nii.gz* in FSLView. Do you see any improvement?

#. Compare the location on the tissue edges (e.g. [133 155 81]) in this QSM map with what you can see in the mean magnitude image *mean_head.nii.gz*. Do the edges match between the two data now?

.. toctree::
   :maxdepth: 1

   Exercise4_answer2

**Congratulations! You have finished all the exercises in this tutorial.** If you still have time left, finish the advanced exercises or experiment with different QSM methods/methods' parameters. 

Advanced Exercise 4.3
^^^^^^^^^^^^^^^^^^^^^

To further improve the quality of the QSM map, some methods, such as Star-QSM, incorporate additional information, e.g. smoothness of the QSM map, during the QSM dipole inversion.

1. Change the **Output basename** to: *~/qsm_tutorial/data/output_qsm/Sepia_star-qsm*.
2. Change the **QSM** method to 'Star-QSM' and press **Start**. It will take about 2 mins to finish.

It is difficult to see the differences between the two QSM maps with the naked eyes. Subtract the two maps so that you can see the differences:

``fslmaths Sepia_tkd-0p15_QSM.nii.gz -sub Sepia_star-qsm_QSM.nii.gz difference_qsm``

3. Display the *difference_qsm.nii.gz* image (dispay window [-0.1,0.1]) in FSLView with *Sepia_star-qsm_QSM.nii.gz* (dispay window [-0.2,0.2]) and *Sepia_tkd-0p15_QSM.nii.gz* (dispay window [-0.2,0.2]) in the output directory. Can you see any difference between the two QSM maps?

.. toctree::
   :maxdepth: 1

   Exercise4_answer3

Back to :ref:`fmritoolkit2019-exercise3`.
