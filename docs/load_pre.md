# Load pre-procedural data

Once SliceTracker starts receiving the data, you will be notified by a message shown below.

![](images/receiving_dicom.png)

SliceTracker concludes transfer completion of the pre-procedural data if no new files were received for 5 seconds. At that point, SliceTracker imports and indexes the received images into the Slicer DICOM database. The progress reporting area provides feedback about ongoing tasks.

![](images/processing_dicom.png)

