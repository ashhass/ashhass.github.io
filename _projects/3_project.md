---
layout: page
title: MP2S
description: Modernizing Public Security Systems.
img: assets/img/20.png
category: work
giscus_comments: false
date: July 20, 2023
---

Crimes/Accidents have unfortunately been a frequent occurrence throughout human history. With the emergence of structured societies, tremendous efforts have been put forth in order to minimize this frequency or prevent it altogether. However, the limited capabilities of humans to predict, attend to or prevent an incident has largely resulted in frustration amongst the public and lack of trust in security systems. We believe that complimenting human efforts with machine efficiency
can enhance the effectiveness of current security systems and thereby increase the public’s trust in them. 

Existing security systems are ineffective due to the constant human monitoring that needs to take
place. This in turn compromises human safety since it requires some sort of human intervention
to stop a possible crime event. Moreover, communication between different parties in order to
finally attend to an incident scene is inefficient, hence automating this process enhances security
tremendously.

<div class="caption">
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/15.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Use Case Diagram
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/18.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/19.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Sequence Diagram
</div>

We propose a system that would learn to detect abnormal behavior from streams of video data by
effectively learning normal data using motion in videos and later singling out any anomalies. Police stations could then be contacted once a situation is observed as dangerous. This can be achieved in the following steps:
<ul>
<li> Extracting dense optical flow maps from videos. </li>
<li> Feeding the extracted map and training a CAE on normal data to reconstruct the flow map. </li>
<li> During inference, video frames with high reconstruction errors are regarded as abnormalities. </li>
<li> Once a series of frames is flagged anomalous, a human observer is notified. </li>
<li> After analyzing the situation, the human observer can hit the alert button (if the situation.
calls for it) and the system connects all concerned bodies (eg. police officers) in a graph like
structure and searches for nearby persons (by locating their coordinates). These nodes are
then notified using their portable phones and can reach the incident location in due time. </li>

</ul>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/16.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/17.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Web Interface
</div>

For building this system, we utilize the concepts of optical flow and image reconstruction through
convolutional autoencoders. First, for every image frame, we extract dense optical flow maps. We
then train autoencoders to learn patterns of flow maps that represent normal motion. However,
the autoencoders only learn the spatial patterns, but since videos have another dimension, namely
temporal dimension, we make use of convolutional LSTMs in order to learn the temporal patterns.
<br> <br>
Once the model is trained, it can be used to detect anomalies in videos by flagging the frames with
higher reconstruction errors since that infers that such motion is abnormal to the pattern learnt
by the model i.e motion pattern occurring in normal videos. Once an anomaly is observed, the
human observer can be notified to either alert concerned departments or ignore the signal if the
motion is regarded as normal. If immediate action needs to take place, the system automatically
notifies the cell phones of concerned persons which are closest to the accident location. To do
this, the system places all concerned bodies in a graph-like structure similar to structures used in
networking platforms such as Facebook and Linkedin. This eases and automates the process of
searching for closeby people and calling for assistance. Connection between nodes is decided based
on the proximity to the accident location. The location of each police officer/vehicle is tracked
using their cell phones on Google Maps. Once the nearest officers are determined, their phones are
notified through an app installed on every officer's cell phone. The graph structure between nodes
will be computed on the fly once an alert has been issued. This is in order to reduce the complexity
and calculation required to track every moving node during a time of inactivity.

Project code can be found here: <a href='https://github.com/ashhass/MP2S_Implementation.git'> MP2S Implementation</a>