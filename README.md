# MappingBand
Mapping Band - it maps Marching Bands. Get it?

NOTE: Models and Report data have been migrated to OneDrive to save on LFS storage. You can find them zipped [here](https://mines0-my.sharepoint.com/:u:/g/personal/lniewohner_mines_edu/EX5_TJw0Vy9PsoBEt-nyAUwB1T1dRSBY3EvBsK0Buynxpg?e=M3JIw5c), valid until my account is terminated after graduation :)

In Marching Band, a drill chart is a fairly simple map showing where band members should stand at different stages of a show. They typically include an indication of when a particular set (a single map) should occur (in terms of measures of music), a reference of a football field in the background, and each person’s position denoted with a letter and number indicating the instrument and person number. A given show may have many sets, collectively called “drill”. Drill typically goes from paper to the field, creating the halftime spectacles we all love. But designing that drill is no easy task.

To aid drill writers in honing their craft, borrowing drill from other writers, and producing maps of actual performances to show to performers, we propose a system which goes the opposite direction: from the field, back to paper. Given a video recording of a performance, this system would pull out frames, locate people and identify instruments they play, and finally place those detected people onto a dot chart

---

The key components we have built into this system:
1. Tuned Optical Character Recognition for identifying the letters and numbers on the field. This is done by fine-tuning the Attention OCR model on a dataset of drill charts.
1. A field detector based mostly on classical computer vision techniques, including a Hough Line Detector and a RANSAC algorithm which robustly pulls out lines which fit the repeating pattern of a football field.
1. A person detector based on the YOLOv8 architecture, which is trained on a dataset of marching band performers. This detector is used to locate people in the video.
