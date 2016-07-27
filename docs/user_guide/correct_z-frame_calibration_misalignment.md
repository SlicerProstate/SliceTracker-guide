# Correct Z-frame calibration misalignment

In case of the Z-frame model not properly aligned with the Z-frame image artifacts, you will need to manually set the slice range where the Z-frame calibration runs on. The following screenshot shows such a misalignment.

![](../images/zframe_misaligned.png)

In order to set the manual start/end indexes, you will need to check "Use manual start/end indexes" as displayed below.

![](../images/zframe_calibration_manual_start_end.png)

## How to figure out slice index
In the lower left corner of the main Slicer user interface you will find a collapsible button "Data Probe". This module can be used to find out the start and end index of the Z-frame image artifacts.

Start index: Scroll to the very first slice, where all artifacts are clearly visible (8 white dots)
End index: Scroll to the very last slice, where all artifacts are clearly visible (8 white dots)

The image below shows where to find the slice index of the current slice. **NOTE:** Make sure to move the cursor within the current slice view, so that the Data Probe module is updated according to it. The Date Probe module will only display values if the cursor is inside that slice view.

![](../images/zframe_dataprobe_slice_index.png)

