Augmented Lagrangian Digital Volume Correlation (ALDVC) Documentation
=======================================

Welcome to the documentation for the Augmented Lagrangian Digital Volume Correlation (ALDVC) code package! Here you will find tutorials, articles, and links to the software manuals. Browse through the available articles using the links to the side.

- Getting Started will help you download the software, install it, and subscribe any future updates.

- The Tutorials section will help you with many basic and advanced topics including topics such as: performing your first ALDVC analysis, performing a mesh convergence study, and performing multiphasic analyses.

- The FAQ section contains common questions that we received during the past years from our users.


.. contents::



Introduction
----------
Digital volume correlation (DVC), the volumetric extension of the popular digital image correlation
(DIC) technique, is a powerful experimental tool for measuring 3D volumetric full-field displacements
and strains. Most current DVC algorithms can be categorized into either local or finite-element-based global methods. As with most experimental approaches, there are drawbacks with
each of these methods. In the local method the subvolume deformations are estimated independently
and the computed displacement field may not necessarily be kinematically compatible.
Therefore, the deformation gradients can be noisy, especially when using small volumetric subsets.
Although the global method often enforces kinematic compatibility, it generally incurs substantially
greater computational costs than its local counterpart, which is especially significant for large volumetric data sets.

Here we present a new hybrid DVC algorithm, called augmented Lagrangian
digital volume correlation (ALDVC) [1]_, which combines the advantages of both the local (fast computation
times) and global (compatible displacement field) methods. This new algorithm builds on
our recent work on the augmented Lagrangian digital image correlation (2D-ALDIC) technique [2]_
(2D-ALDIC MATLAB code is avalable on Mathworks File Exchange: [3]_) and solves the general motion optimization problem by using the alternating direction method of multipliers (ADMM) [4]_. We demonstrated that our ALDVC algorithm has high accuracy and precision while maintaining low computational cost, and is a significant improvement compared to current local and global DVC methods [1]_. For a review of both local and global DVC methods, and details of this new proposed ALDVC
method, please see Fig. 1 and our paper [1]_ (full text can also be accessed via [5]_).


Some advantages of our ALDVC algorithm are highlighted below:
- (i) It is a fast algorithm using distributed parallel computing for a global nonconvex optimization.
(ii) Global kinematic compatibility is added as a global constraint in augmented Lagrangian form,
and solved using the Alternating Direction Method of Multipliers (ADMM) scheme.
(iii) Both displacement fields and affine deformation gradients are computed at the same time.
(iv) Since global compatibility is enforced the user does not need to choose a specific displacement
smoothing filters.
(v) It works well with compressed images and can include adaptive mesh refinement [6].
(vi) It can solve an image sequence with multiple time frames 1.

Getting Started
----------

.. image:: docs/images/aldvc_logo.png
    :width: 90%

Installation
------------

Section title #2
-----------



References
-----------
.. [1] J Yang, L Hazlett, A.K. Landauer, and C. Franck. Augmented Lagrangian Digital Volume Correlation. Experimental Mechanics, 2020.
.. [2] J Yang and K Bhattacharya. Augmented Lagrangian Digital Image Correlation. Experimental Mechanics, 59:187-205, 2019.
.. [3] 2D ALDIC code. https://www.mathworks.com/matlabcentral/fileexchange/70499-augmentedlagrangian-digital-image-correlation-and-tracking.
.. [4] S Boyd, N Parikh, E Chu, B Peleato, and J Eckstein. Distributed optimization and statistical learning via the alternating direction method of multipliers. Machine Learning, 3:1-122, 2010.
.. [5] https://www.researchgate.net/publication/343676441 Augmented Lagrangian Digital Volume Correlation.
.. [6] J Yang and K Bhattacharya. Combining image compression with digital image correlation. Experimental Mechanics, 59:629-642, 2019.
.. [7] 3D Volume Interpolation with ba interp3. https://www.mathworks.com/matlabcentral/fileexchange/21702-3d-volume-interpolation-with-ba_interp3-fast-interp3-replacement.
.. [8] MATLAB Support for MinGW-w64 C/C++ Compiler. https://www.mathworks.com/matlabcentral/fileexchange/52848-matlab-support-for-mingw-w64-c-c-compiler.
.. [9] MathWorks: MinGW-w64 Compiler. https://www.mathworks.com/help/matlab/matlab external/install-mingw-support-package.html.
.. [10] E Bar-Kochba, J Toyjanova, E Andrews, K-S Kim, and C Franck. A fast iterative digital volume correlation algorithm for large deformations. Experimental Mechanics, 55:261-274, 2015.
.. [11] AK Landauer, M Patel, DL Henann, and C Franck. A q-factor-based digital image correlation algorithm (qDIC) for resolving finite deformations with degenerate speckle patterns. Experimental Mechanics, 58:815-830, 2018.
.. [12] FIDVC code. https://github.com/FranckLab/FIDVC.
.. [13] qFIDVC code. https://github.com/FranckLab/qFIDVC.
.. [14] MathWorks Help Center: parpool. https://www.mathworks.com/help/distcomp/parpool.html.
.. [15] PL Reu, E Toussaint, E Jones, HA Bruck, M Iadicola, R Balcaen, DZ Turner, T Siebert, P Lava, and M Simonsen. DIC challenge: Developing images and guidelines for evaluating accuracy and resolution of 2D analyses. Experimental Mechanics, 58:1067-1099, 2018.


#ALDVC documentation link is available here:
https://aldvc-doc.readthedocs.io/en/latest/#

#Read the tutorial here:
#https://docs.readthedocs.io/en/stable/tutorial/
