# Intra-procedural tracking of targets

Intra-procedural phase of the workflow is driven by the intra-procedural image data. The sequence of processing steps and the corresponding types of image series is the following:  
1. Z-frame calibration: in this step, the Z-frame device attached to the transperineal biopsy template is registered with the coordinate frame of the scanner. In AMIGO, Z-frame image series will have the name "AX TSE T2 COVER TEMPLATE" \(`ZFrame` image\).  
2. Registration of the pre-procedural T2-weighted series to the intra-procedural imaging and re-identification of the planned target locations. In AMIGO, initial, high-resolution intra-procedural T2-weighted image will have the name "AXIAL T2 COVER PROSTATE" \(`CoverProstate` image\).  
3. Tracking of the biopsy targets in the needle confirmation scans. In AMIGO, needle confirmation images will be called either "AX TSE T2 GUIDANCE FOR NEEDLE" \(T2-weighted images\) \(`Needle` image\) or "AX 3D VIBE" \(`Vibe` image\).

![](/assets/intra_procedural_overview.png)

As new images are received, they will be added to the series selector in the SliceTracker control panel, right under the target list. The image currently selected will be shown in the slice viewers. Each item in the series selector is color-coded:

* yellow: new item that has not been processed \(note that some images, such as localizer, do not need to be processed, or can be skipped\)
* green: item has been processed, and the processing result has been accepted
* red: item has been rejected by the operator \(for example, due to poor image quality, or poor registration result\)
* grey: item has been skipped \(for example, when a certain image series has been collected that does not require processing\)



