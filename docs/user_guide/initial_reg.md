# Cover prostate registration and re-identification of the planned targets

Once Z-frame registration is confirmed, and `CoverProstate` image is acquired, the grid of the needle paths of the template will be shown in overlay of the cover prostate image.

**IMPORTANT**: Notify the clinical lead of the procedure once you reach this point. This is important to confirm coverage of the gland.

After coverage confirmation, proceed with target re-identification by clicking "Track targets" button.

To track targets, you will first prepare a rough segmentation of the prostate gland. Your mouse cursor should automatically show fiducial placement icon![](../images/fiducialmode_icon.png). 

Click in the vicinity of the prostate capsule boundary to make sure the green outline approximates the capsule. 

![](../images/volumeclip_points.png)

You will need to place points on multiple slices before the green outline appears.

![](../images/volumeclip_contour.png)

Buttons in the module panel provide the following features:

|<center>Button|Description|
|--|--|
|<center><img src="../../SliceTracker/Resources/Icons/icon-greenCheck.png" width="20">|finish segmentation|
|<center><img src="../../SliceTracker/Resources/Icons/icon-undo.png" width="20">,<img src="../../SliceTracker/Resources/Icons/icon-redo.png" width="20">|undo/redo point placement|
|<center><img src="../../SliceTracker/Resources/Icons/icon-cancelSegmentation.png" width="20">|cancel segmentation|


After prostate segmentation has been completed, SliceTracker will decide based on the availability of pre-procedural image data about which steps to display next. 

**NO PRE-PROCEDURAL DATA AVAILABLE?**: see [Continue without pre-procedural data](continue_without_preop.md)

If pre-procedural image data is available, the layout will automatically change to show the pre-procedural (planning) T2-weighted image on the left, and the intra-procedural `CoverProstate` image on the right. Both viewers will show the segmentation outline as overlays. Confirm that segmentations are similar (no large portions of the gland are skipped in either of the images).

Click "Apply registration" once segmentation consistency is confirmed.

Upon completion of registration, you will be presented with a layout showing biopsy plan on the left, and registration result on the right.

**IMPORTANT**: Confirm the accuracy of registration with the clinical lead of the procedure!

You can use the following tools to verify registration accuracy:
* "Rock" checkbox: slowly fade back and forth between the registered planning image and the `CoverProstate` image.
* "Flicker" checkbox: quickly flip back and forth between the registered planning image and the `CoverProstate` image.
* "Reveal cursor" button: show mosaic of the registered planning image and the `CoverProstate` image at the cursor location.

| ![Biopsy template assembly (left) and Z-frame. MR-visible capsules are of yellow color within a plexiglass enclosure.](../images/registration_evaluation.png) | ![Z-frame and needle template models before calibration ](../images/reveal_cursor.png) |
| -- | -- |
| User interface elements to support registration result evaluation. | Reveal cursor in action. |


**If registration result is satisfactory**: Click "Approve", communicate the needle hole and insertion depth to the clinical lead.

**If registration result is NOT satisfactory**, here is what you can try:
* _check different registration types (Rigid or Affine)_: if any of these is satisfactory - approve it.
* _move the target to a more suitable location_: double-click the corresponding target row in the target table, which will toggle target move mode. You can then scroll to the desired slice for the target, and place on the updated location.
* _re-do segmentation of the prostate and re-run registration_: this can be done by clicking "Retry" button. Note that this approach is most time-consuming.
