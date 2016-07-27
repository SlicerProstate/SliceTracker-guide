# Target initialization

SliceTracker supports two modes of operation.

1. Re-identification of the biopsy targets placed on the pre-procedural T2-weighted MRI. This is done by means of deformable registration of the pre-procedural T2-weighted image to the intra-procedural `CoverProstate` image.
2. Initialization of the biopsy targets directly in the intra-procedural `CoverProstate` scan. This situation happens when pre-procedural data is not available, or is of insufficient quality for target localization.

Next two section will familiarize you with these two scenarios.