---
layout: page
title: Quark Gluon Reconstruction
description:
img: assets/img/qg_thumbnail.png
importance: 2
category: work
giscus_comments: false
---

In High Energy Physics, achieving both accurate and fast simulation of particle physics processes is critical.The primary aim of a fast simulator is to efficiently map the events from the generation level to reconstruction level. While Variational Autoencoders (VAEs) have been successful for reconstruction level tasks, they generally use Convolutions which are good for normal RGB channel images that are highly structured and have a good sense of locality. If we change the pixels the image loses its meaning. Given that the data coming from detectors is non-Euclidean by nature, transforming this data into graphs and learning their properties is a better choice.
This task involves training an Graph Variational Autoencoder to learn and reconstruct the representations of Quark/Gluon events.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/qg.png" title="example image" class="img-fluid rounded z-depth-1" height=700 width=900 align="center" %}
    </div>
</div>
<div class="caption">
    A sample representation of the 3 channels (Tracks,Ecal,Hcal) present in a Quark and a representation of the 3 channels combined.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/gvae_tracks.png" title="example image" class="img-fluid rounded z-depth-1" height=700 width=700 %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/gvae_hcal.png" title="example image" class="img-fluid rounded z-depth-1" height=700 width=700 %}
    </div>
</div>
<div class="caption">
    On the left, reconstruction of Tracks channel and comparision with input. Right, reconstruction of Hcal channel and comparision with input.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/gvae_ecal.png" title="example image" class="img-fluid rounded z-depth-1" height=700 width=700 %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/gvae_combined.png" title="example image" class="img-fluid rounded z-depth-1" height=700 width=700 %}
    </div>
</div>
<div class="caption">
    On the left, reconstruction of Ecal channel and comparision with input. Right, reconstruction of all channels combined channel and comparision with input.
</div>

For more details refer to [DeepFalcon](https://github.com/pratyush-1/DeepFalcon) and [Genie](https://github.com/pratyush-1/Genie) which also compares diffusion models, autoencoders and Graph Variational Autoencoders performance.

