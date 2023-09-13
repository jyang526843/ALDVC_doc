.. _introduction:

==================
Introduction
==================

Overview
-----------------------

Digital volume correlation (DVC), the volumetric extension of the popular digital image correlation
(DIC) technique, is a powerful experimental tool for measuring 3D volumetric full-field displacements
and strains. Most current DVC algorithms can be categorized into either local or finite-element-based global methods. As with most experimental approaches, there are drawbacks with
each of these methods. In the local method the subvolume deformations are estimated independently
and the computed displacement field may not necessarily be kinematically compatible.
Therefore, the deformation gradients can be noisy, especially when using small volumetric subsets.
Although the global method often enforces kinematic compatibility, it generally incurs substantially
greater computational costs than its local counterpart, which is especially significant for large volumetric data sets.

Here we present a new hybrid DVC algorithm, called augmented Lagrangian
digital volume correlation (ALDVC) `[Yang2020]`_, which combines the advantages of both the local (fast computation
times) and global (compatible displacement field) methods. This new algorithm builds on
our recent work on the augmented Lagrangian digital image correlation (2D-ALDIC) technique `[Yang2019a]`_
(2D-ALDIC MATLAB code is avalable on Mathworks File Exchange `[ALDIC Mathworks link]`_ or Github `[ALDIC Github link]`_) and solves the general motion optimization problem by using the alternating direction method of multipliers (ADMM) `[Boyd2010]`_. We demonstrated that our ALDVC algorithm has high accuracy and precision while maintaining low computational cost, and is a significant improvement compared to current local and global DVC methods `[Yang2020]`_. For a review of both local and global DVC methods, and details of this new proposed ALDVC
method, please see :numref:`img_dvc_comp` and our paper `[Yang2020]`_ (full text can also be accessed here `[ALDVC ResearchGate]`_).


Advantages of the ALDVC algorithm
-----------------------

* [1] It is a *fast* algorithm using *distributed parallel* computing for a global nonconvex optimization.
* [2] *Global kinematic compatibility* is added as a global constraint in augmented Lagrangian form, and solved using the *Alternating Direction Method of Multipliers (ADMM)* scheme.
* [3] Both displacement fields and affine deformation gradients are computed at the same time.
* [4] Since global compatibility is enforced the user does not need to choose a specific displacement smoothing filters.
* [5] It works well with compressed images and can include *adaptive mesh* refinement `[Yang2019b]`_.
* [6] It can solve an image sequence with multiple time frames and handle large finite deformations.


A schematic showing the difference between ALDVC and other conventional DVC methods is summarized in :numref:`img_dvc_comp`.



.. _img_dvc_comp:

.. figure:: ./img/fig_dvc_illustraion_figs1-3.png
   :alt: blabla
   :align: center
   :width: 90 %

   **Comparison between different DVC methods.** (a) Schematic showing a volumetric DVC reference image f(**X**), with a general speckle pattern, deforming into the deformed image g(**y** (**X**) ) under some mapping **y** and the change of variables involved within the IC-GN iteration in the local subvolume DVC method. **X** and **y** coordinates are in the reference and deformed images, respectively. **z** coordinates are in current IC-GN iteration. (b) A schematic comparison between the local DVC method (left), where all the subvolumes are analyzed independently, and the global DVC method (right), where a global basis set is used to represent the full-field deformation.














References
-----------


.. _[Yang2020]:

J Yang, L Hazlett, A.K. Landauer, and C. Franck. Augmented Lagrangian Digital Volume Correlation. Experimental Mechanics, 60:1205-1223, 2020.


.. _[Yang2019a]:

J Yang and K Bhattacharya. Augmented Lagrangian Digital Image Correlation. Experimental Mechanics, 59:187-205, 2019.

.. _[ALDIC Mathworks link]:

2D ALDIC MATLAB code Mathworks FileExchange link. https://www.mathworks.com/matlabcentral/fileexchange/70499-augmentedlagrangian-digital-image-correlation-and-tracking.

.. _[ALDIC GitHub link]:

2D ALDIC MATLAB code Github link. https://github.com/jyang526843/2D_ALDIC.

.. _[Boyd2010]:

S Boyd, N Parikh, E Chu, B Peleato, and J Eckstein. Distributed optimization and statistical learning via the alternating direction method of multipliers. Machine Learning, 3:1-122, 2010.

.. _[ALDVC ResearchGate]:

ResearchGate link for "Augmented Lagrangian Digital Volume Correlation": https://www.researchgate.net/publication/343676441.

.. _[Yang2019b]:

J Yang and K Bhattacharya. Combining image compression with digital image correlation. Experimental Mechanics, 59:629-642, 2019.


