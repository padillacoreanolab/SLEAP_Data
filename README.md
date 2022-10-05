# Training Instructions

### Bottom-up:
~~~
sleap-train ~/SLEAP_Data/training_profiles/baseline_medium_rf.bottomup.json ~/SLEAP_Data/labeled_data/labels_mouse_instances.v012.pkg.slp
~~~

### Top-down:
~~~
sleap-train ~/SLEAP_Data/training_profiles/baseline_medium_rf.topdown.json ~/SLEAP_Data/labeled_data/labels_mouse_instances.v012.pkg.slp
~~~
~~~
sleap-train ~/SLEAP_Data/training_profiles/baseline.centroid.json ~/SLEAP_Data/labeled_data/labels_mouse_instances.v012.pkg.slp
~~~
## Inference:

### Bottom-up:
~~~
sleap-track ~/SLEAP_Data/videos/video.AVI --video.dataset video --input_format channels_last --tracking.tracker flow --tracking.similarity centroid --tracking.match greedy --tracking.clean_instance_count 2 --tracking.target_instance_count 2 -m ~/SLEAP_Data/models/baseline_medium_rf.bottomup/
~~~

### Top-down:
~~~
sleap-track ~/SLEAP_Data/videos/video.AVI --video.dataset video --video.input_format channels_last --tracking.tracker flow --tracking.similarity centroid --tracking.match greedy --tracking.clean_instance_count 2 -m ~/SLEAP_Data/models/baseline_medium_rf.topdown -m ~/SLEAP_Data/models/baseline.centroid
~~~
