# Instructions

## Training

### Bottom-up:
~~~
sleap-train ~/SLEAP_Data/training_profiles/baseline_medium_rf.bottomup.json ~/SLEAP_Data/Labeled_data/New_Instances/labels_mouse_instances.v003.pkg.slp
~~~

### Top-down:
~~~
sleap-train ~/SLEAP_Data/training_profiles/baseline_medium_rf.topdown.json ~/SLEAP_Data/Labeled_data/New_Instances/labels_mouse_instances.v003.pkg.slp
~~~
~~~
sleap-train ~/SLEAP_Data/training_profiles/baseline.centroid.json ~/SLEAP_Data/Labeled_data/New_Instances/labels_mouse_instances.v003.pkg.slp
~~~
## Inference:

### Bottom-up:
~~~
sleap-track ~/SLEAP_Data/videos/video.AVI --video.dataset video --input_format channels_last --tracking.tracker simple --tracking.similarity iou --tracking.match hungarian --tracking.clean_instance_count 2 --tracking.target_instance_count 2 -m ~/SLEAP_Data/models/New_Instances/baseline_medium_rf.bottomup_new_data/
~~~

### Top-down:
~~~
sleap-track ~/SLEAP_Data/videos/video.AVI --video.dataset video --video.input_format channels_last --tracking.tracker simple --tracking.similarity centroid --tracking.clean_instance_count 2 -m ~/SLEAP_Data/models/New_Instances/baseline_medium_rf.topdown -m ~/SLEAP_Data/models/New_Instances/baseline.centroid
~~~
