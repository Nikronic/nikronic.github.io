---
layout: page
title: Deep Halftoning
description: Deep context-aware descreening and rescreening of halftone images via end-to-end deep learning method.
img: assets/img/de(re)screening01.webp
importance: 2
category: work
giscus_comments: true
github: https://github.com/Nikronic/Deep-Halftoning
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/de(re)screening01.webp" title="Halftoning and Rescreening example" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Halftoning and Rescreening example
</div>

This project pertains automated Descreening process. Descreening is the task that we try to reconstruct the <a href="https://en.wikipedia.org/wiki/Halftone">halftoned</a> image (which is the mandatory process to interact images with printers, scanners, monitors, etc) meanwhile reducing the amount of data loss. For more info, please see the <a href="https://doi.org/10.1145/3197517.3201377">original paper</a>.

<ul>
    <li>First and the only fully open source implementation of this paper, in PyTorch</li>
    <li>The implementation can be divided into below separate projects:</li>
    <ul>
        <li>
            <a href="https://github.com/Nikronic/CoarseNet">CoarseNet</a>: Modified version of U-Net architecture to work as a low-pass filter to remove halftone patterns
        </li>
        <li>
            <a href="https://github.com/Nikronic/DetailsNet">DetailsNet</a>: A deep CNN generator and two discriminators which are trained simultaneously to improve image quality by adding details to it
        </li>
        <li>
            <a href="https://github.com/Nikronic/EdgeNet">EdgeNet</a>: A simple CNN model to extract Canny edge features to preserve details
        </li>
        <li>
            <a href="https://github.com/Nikronic/ObjectNet">ObjectNet</a>: Modified version of "Pyramid Scene Parsing Network" to only return 25 major classified segments out of 150
        </li>
        <li>
            <a href="https://github.com/Nikronic/Halftoning-Algorithms">Halftoning Algorithms</a>: Implementation of some of the halftone algorithms provided in most recent digital color halftoning books as ground truth
        </li>
    </ul>
</ul>

You can find the implementation on <a href="https://github.com/Nikronic/Deep-Halftoning">Github</a>.
