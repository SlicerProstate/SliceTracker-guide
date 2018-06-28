# Developer guide

The following sections summarize some of the details about the overall system architecture and components used within the software.

## Plugins
SliceTracker was designed to be flexible and easily extensible by using a plugin architecture. New functionality can be added with minimal effort by inheriting from a SliceTrackerPlugin class. Derived classes have access to a session singleton, which controls the flow of data, keeps track of incoming DICOM data and reacts to case specific events (e.g. case started) as well as user input. The following SliceTracker plugins are available to date: 

* _Automatic Segmentation_ is a logic-based plugin that has no user interface. Other registration algorithms can be introduced.
* _Manual Segmentation_ provides a user interface for manual segmentation by using the 3D Slicer Segment Editor module effect SurfaceCut. A surface is created from points set by the user for mimicking the contour of the prostate gland.
* _TargetTable_ displays information regarding targets as well as computed template grid holes and depth for every single target. For needle guidance images, calculated hole/depth can change over the course of a tpMRgBx case. Some color-coding was implemented to display changes in calculated hole/depth to the user.
* _CaseManager_ keeps track of case directories and invokes case specific events; (e) TargetDisplacementCharting visualizes I/S, P/A, L/R and 3-D displacement of a selected target as individual plots.
* _Training_ offers a user interface showing buttons for simulating the reception of pre -and intra-procedural imaging data.

## mpReview
Preprocessing of planning images is done by the [3D Slicer extension mpReview](https://github.com/SlicerProstate/mpReview), which has been integrated into the SliceTracker specific tpMRgBx workflow. Based on mpMRI, the interventionalist identifies suspicious lesions. After target identification, prostate gland segmentation can either be done manually in mpReview or automatically by SliceTracker using the segmentation approach provided by DeepInfer.

## Events
An event-based approach was adopted for keeping SliceTracker steps and plugins loosely coupled. Session, steps and plugins can listen to events of other classes as well as invoke events of their own. As an example, a plugin listens to the event when a case is closed. Upon invocation of that event, the plugin can clean its own internal data structure getting ready for new data.

## SlicerDevelopmentToolbox
During SliceTracker development, we noticed a high degree of code duplication in core components used across varying 3D Slicer extensions. [SlicerDevelopmentToolbox (SDT) extension](http://sdt.readthedocs.io/en/latest/) provides a toolbox to extension developers that aims to keep code short and clean without having hundreds of lines of repetitive code. SDT is a Python API offering mixins, widgets, helpers, constants, decorators, and other classes. Goal of SDT is to help developers to create new extensions and maintain extensions over time. This extension can be found on the 3D Slicer extension manager.

## Directory structure and file formats
DICOM images, pre-processed data (targets, segmentations, volumes), and registration results are saved in dedicated directories that were created with initialization of a tpMRgBx case. All data entities are stored using open formats. SliceTracker is required to save intermediate results as well as load them (e.g. in the event of failure, to continue the case). We decided to use the JavaScript Object Notation (JSON) file format for keeping track of persistent data location and including qualitative details about: 
* procedure: start and completion time; 
* registration results: approval status, consent, timestamps for series reception, status change and registration start/end; modification of targets. 
* segmentation: manual or automatic as well as start and completion times.
