.. _introduction:

=====
Introduction
=====

Digital volume correlation (DVC), the volumetric extension of the popular digital image correlation
(DIC) technique, is a powerful experimental tool for measuring 3D volumetric full-field displacements
and strains. Most current DVC algorithms can be categorized into either local or finite-element-based global methods. As with most experimental approaches, there are drawbacks with
each of these methods. In the local method the subvolume deformations are estimated independently
and the computed displacement field may not necessarily be kinematically compatible.
Therefore, the deformation gradients can be noisy, especially when using small volumetric subsets.
Although the global method often enforces kinematic compatibility, it generally incurs substantially
greater computational costs than its local counterpart, which is especially significant for large volumetric data sets.

Here we present a new hybrid DVC algorithm, called augmented Lagrangian
digital volume correlation (ALDVC) `[1]`_, which combines the advantages of both the local (fast computation
times) and global (compatible displacement field) methods. This new algorithm builds on
our recent work on the augmented Lagrangian digital image correlation (2D-ALDIC) technique `[2]`_
(2D-ALDIC MATLAB code is avalable on Mathworks File Exchange: :ref:`[3]`) and solves the general motion optimization problem by using the alternating direction method of multipliers (ADMM) :ref:`[4]`_. We demonstrated that our ALDVC algorithm has high accuracy and precision while maintaining low computational cost, and is a significant improvement compared to current local and global DVC methods :ref:`[1]`. For a review of both local and global DVC methods, and details of this new proposed ALDVC
method, please see :ref:`Fig. 1` and our paper :ref:`[1]` (full text can also be accessed via :ref:`[5]`).


Some advantages of our ALDVC algorithm are highlighted below:
    - [i] It is a *fast* algorithm using *distributed parallel* computing for a global nonconvex optimization.
    - [ii] *Global kinematic compatibility* is added as a global constraint in augmented Lagrangian form, and solved using the *Alternating Direction Method of Multipliers (ADMM)* scheme.
    - [iii] Both displacement fields and affine deformation gradients are computed at the same time.
    - [iv] Since global compatibility is enforced the user does not need to choose a specific displacement smoothing filters.
    - [v] It works well with compressed images and can include *adaptive mesh* refinement :ref:`[6]`.
    - [vi] It can solve an image sequence with multiple time frames and handle large finite deformations.



 .. include:: references.rst