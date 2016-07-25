# Intra-procedural tracking of targets

Intra-procedural phase of the workflow is driven by the intra-procedural image data. The sequence of processing steps and the corresponding types of image series is the following:
1. Z-frame calibration: in this step, z-frame device attached to the transperineal biopsy template is registered with the coordinate frame of the scanner. In AMIGO, Z-frame image series will have the name "AX TSE T2 COVER TEMPLATE".
2. Registration of the pre-procedural T2-weighted series to the intra-procedural imaging and re-identification of the planned target locations. In AMIGO, initial, high-resolution intra-procedural T2-weighted image will have the name "AXIAL T2 COVER PROSTATE".
3. Tracking of the biopsy targets in the needle confirmation scans and visualization of the needle path. In AMIGO, needle confirmation images will be called either "AX TSE T2 GUIDANCE FOR NEEDLE" (T2-weighted images) or "AX 3D VIBE".