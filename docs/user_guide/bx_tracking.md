# Intra-procedural tracking of targets

Intra-procedural phase of the workflow is driven by the intra-procedural image data. The sequence of processing steps and the corresponding types of image series is the following:
1. Z-frame calibration: in this step, z-frame device attached to the transperineal biopsy template is registered with the coordinate frame of the scanner.
2. Registration of the pre-procedural T2-weighted series to the intra-procedural imaging and re-identification of the planned target locations.
3. Tracking of the biopsy targets in the needle confirmation scans and visualization of the needle path.

## Z-frame calibration

Z-frame is a calibration device that consists of a plastic enclosure that attaches rigidly to the template assembly, and 7 elongated capsules containing liquid that gives bright signal in certain types of MR images. 

Given the known configuration of these capsules and their appearance in the image, it is possible to align the known configuration with the corresponding image artifacts, and thus establish a transformation between the biopsy template and the scanner coordinate system.

| ![Biopsy template assembly (left) and z-frame. MR-visible capsules are of yellow color within a plexiglass enclosure.](../images/zframe.png) | ![Z-frame and needle template models before calibration ](../images/zframe_unregistered_annotated.png) |
| -- | -- |
| Biopsy template assembly (left) and z-frame. MR-visible capsules are of yellow color within a plexiglass enclosure. | Z-frame (yellow arrow) and needle tracks of the template (blue arrow) models before calibration. Red arrow points to the artifacts corresponding to the z-frame in the image slice. |

Once z-frame is received, it will be automatically loaded and displayed. To perform z-frame calibration, you will need to define the region of interest (ROI) in the image corresponding to the location of the z-frame artifacts. ROI placement mode will be activated automatically once z-frame image is loaded, and the mouse pointer icon  ![](../images/roi_icon.png) will reflect this. 

With the ROI mode enabled, click once in the center of the group of bright dots corresponding to the z-frame, and once in the corner just outside that group. Make sure all dots are within the rectangular selection area, as shown in the figure below (arrows indicate the center and corner where you would click to define the ROI).

![](../images/zframe_roi.png)

Once you confirm that all dots are within the ROI, click "Run ZFrame Registration" in the module control panel.

Once z-frame calibration is completed, 3D viewer will show the co-registered position of the image. 

**IMPORTANT**: Verify that z-frame calibration was completed correctly by confirming the alignment of the z-frame model with the z-frame image artifacts, both in 2D and 3D views. In the 2D view, intersections of the z-frame model with the image will be indicated by yellow outlines. Those must closely follow the bright artifacts of the z-frame, as shown in the figure below.

![](../images/zframe_verification.png)

You must confirm registration accuracy by clicking "Confirm registration accuracy" button in the SliceTracker panel in order to proceed with the next steps of the workflow.

