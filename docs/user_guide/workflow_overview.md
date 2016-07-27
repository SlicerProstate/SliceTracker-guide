# Workflow overview

The SliceTracker workflow consists of the two phases: preparation of the biopsy plan and intra-procedural tracking of the biopsy targets.

**Preparation phase** is concerned with the processing of the multi-parametric MRI (mpMRI) obtained prior to the biopsy procedure. It includes segmentation of the prostate gland, correction of the intensity inhomogeneity (if endorectal coil was used during image acquisition), and identification of the biopsy targets.

Note that the **preparation phase is optional**, although it will typically be necessary. In situations where no pre-procedural imaging data is available, it is possible to directly place the targets on the intra-procedural images and track those through the course of the procedure. 

The goal of the **intra-procedural phase** is to provide assistance with the sampling of the tissue from the areas corresponding to the biopsy targets. As the first step of this phase, biopsy template needs to be registered to the patient image coordinate frame. Next, deformable registration is applied to register pre-procedural structural scan of the prostate to the intra-procedural image, enabling re-identification of the biopsy targets in the intra-procedural data. After that, with every subsequent image confirming the placement of the biopsy needle, registration is applied to update the locations of the targets to compensate for the intra-procedural motion and deformation of the prostate gland.

### Prerequisites

It is assumed that the operator
* is familiar with the prostate anatomy and its appearance in MRI (most importantly, on T2-weighted MRI)
* has basic training in 3D Slicer
* has relevant expertise, or is working closely with the interventional radiologist who can interpret multi-parametric MRI
* is familiar with the clinical workflow of the MRgBx procedure

At the moment, this guide is targeting an operator that is working in the settings of the [Advanced Multi-modality Image Guided Operating suite (AMIGO)](http://ncigt.org/AMIGO) at the Brigham and Women's Hospital. This guide may not cover some of the details related to the usage of the module that are not applicable during AMIGO procedures.


