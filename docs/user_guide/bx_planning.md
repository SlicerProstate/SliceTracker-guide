# Biopsy plan preparation

To prepare the biopsy plan, you need to:

1. create a new case
2. load the pre-procedural data
2. prepare pre-procedural data

We will walk you through those steps.

**WARNING**: you must complete biopsy plan preparation before the intra-procedural images could be sent to SliceTracker!

### Creating a new case
As the first step, create a new case with the "New case" button in the SliceTracker console. This will initialize the layout of the directories for the data, and will start the process of listening for the incoming DICOM images. 

![](../images/slicetracker_initial.png)

**Advanced**: Case Directory Settings panel can be used to change the default location of where cases will be stored.

Once the new case is initiated, you should see the message indicating that SliceTracker is waiting for the incoming DICOM data.

![](../images/listener_started.png)

**Important** When prompted about whether you want to end other DICOM listeners running, answer "Yes"! Otherwise, you will not be able to proceed!

The listener will be running on port 11112. You will need to configure your sender of DICOM data accordingly. 

**Advanced**: If you are unable to change the settings (i.e., port) of how the data is sent to the computer running SliceTracker, you can use [a convenience script we provide](https://github.com/SlicerProstate/SliceTracker/blob/master/SliceTracker/SliceTrackerUtils/watch.py) to watch and continuously send DICOM data from a directory to SliceTracker DICOM listener.
* to send files from ```LocalDirectory``` to the instance of SliceTracker running on the same machine:
```
$ python watch.py -d LocalDirectory 
```
* to send files files from ```LocalDirectory``` to the instance of SliceTracker running on IP address 10.0.0.1:
```
$ python watch.py -d LocalDirectory -h 10.0.0.1
```
This convenience script will monitor the content of the directory being watched and all of the sub-directories.

### Loading the pre-procedural data

Once SliceTracker starts receiving the data, you will be notified by a message shown below.

![](../images/receiving_dicom.png)

SliceTracker will conclude that all the pre-procedural data has been received after no new files are received for certain time. At that moment, the files received will be imported and indexed into Slicer DICOM database. You will be notified about this process with the message below.

![](../images/processing_dicom.png)

### Preparing pre-procedural data

Once the pre-procedural data is received, you will be guided through the steps to perform data annotation. If you annotate the data for the first time, you will be prompted to enter you last name and confirm certain settings, for book-keeping purposes. Accept the defaults if unsure how to proceed.

#### Display the series of interest

To annotate the data, first check the series of interest in the "Study selection" tab. When done, proceed to the "Segmentation" tab. 

![](../images/mpreview.png)

All of the series you selected will be loaded in the viewers, and shown in the same plane reformat. Once in the Segmentation tab, choose T2-weighted axial series as the Reference image. This will configure the Slicer viewer layout as follows:

![](../images/viewers_configured.jpg)

* all of the series selected in the previous tab are shown
* each of the viewers is using the same reformat plane
* scroll/zoom/pan is synchronized over the viewers
* if one of the series is a dynamic series (such as Dynamic Contrast Enhanced (DCE) MRI), you can use the MultiVolumeExplorer panel to display the time curve at the mouse pointer location, and trigger cine mode for the series visualization.

![](../images/dynamic_plot.png)

#### Adjust window/level and place targets

Use "Add Structure" button to add a new structure you want to segment (you should at least segment the prostate ("Whole Gland" label in the structures list).

Click the Window Level effect button ![](../images/wl_icon.png). Update the window/level for each of the viewers as necessary.

Click the Fiducials placement button in the Slicer toolbar, and place targets by clicking in the slice viewers.

![](../images/fiducials_placement.png)

TODO: check if the fiducials list should be explicitly selected after placing the targets!

#### Segment prostate gland in T2-weighted series

To segment the prostate gland, you will first contour the gland in every other slice using the Pencil tool ![](../images/pencil_effect.png). Activate the tool by clicking the Pencil icon. Start drawing by clicking the left mouse button. Close the contour by clicking the right mouse button or the Enter key. You can use Undo/Redo buttons ![](../images/undoredo_buttons.png) if you made a mistake (after [this bug](https://github.com/SlicerProstate/mpReview/issues/135) is resolved).

Once every other slice is contoured, use Dilation effect ![](../images/dilate_effect.png) to fill the empty slices. Click the Dilate icon, after that click Apply button.

Once the prostate is segmented in T2-weighted series and the biopsy targets are localized, activate the Completion tab and click Save button. Once this is done, you will return to the SliceTracker and will wait for the intra-procedural DICOM data to continue with the workflow.