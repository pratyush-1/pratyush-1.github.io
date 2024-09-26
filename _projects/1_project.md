---
layout: page
title: SAM-PM Enhancing Video Camouflaged Object Detection
description: 
img: assets/img/publication_preview/video.gif
importance: 1
category: work
# related_publications: Meeran_2024_CVPR
---

Published at **[CVPR 2024 Workshop on Pixel Level Video Understanding in the Wild Challenge](https://openaccess.thecvf.com/content/CVPR2024W/PVUW/papers/Meeran_SAM-PM_Enhancing_Video_Camouflaged_Object_Detection_using_Spatio-Temporal_Attention_CVPRW_2024_paper.pdf)**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cvpr.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div> 
</div>
 <div class="caption">
   Comparison of mask predictions between ground truth (GT), SAM-PM (Ours), and SLT-Net.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/prop.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div> 
</div>
 <div class="caption">
   Architecture of the proposed Propagation Module (PM).
</div>

## Methodology
The proposed **SAM-PM** framework adapts the Segment Anything Model (SAM) for the **Video Camouflaged Object Detection (VCOD)** task. SAM-PM consists of two main components: the **Temporal Fusion Mask Module (TFMM)** and the **Memory Prior Affinity Module (MPAM)**.
    
1. **Temporal Fusion Mask Module (TFMM)**: This module enhances temporal information by integrating mask embeddings from multiple frames. It uses a spatio-temporal cross-attention mechanism to create temporally enriched mask embeddings.
2. **Memory Prior Affinity Module (MPAM)**: MPAM utilizes the temporally infused mask embeddings from TFMM along with image embeddings from the current and previous frames. It applies affinity to strengthen temporal consistency in mask predictions.
SAM-PM operates in a **semi-supervised manner**, where only the first frame's ground truth mask is used for training. The framework keeps SAM's weights frozen and trains only the SAM-PM components, ensuring **parameter efficiency** with less than 1 million parameters. 

During training and inference, SAM-PM updates its memory with new frames and their predicted masks while discarding outdated data to maintain temporal coherence. 