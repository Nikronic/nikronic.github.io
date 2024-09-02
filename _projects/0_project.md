---
layout: page
title: CVFE
description: Canada Visa Form Extraction (CVFE) is a tool set to extract and transform Canada visa forms (IMM 5257 E and IMM 5645 E) into structured tabular format.
img: assets/img/cvfe-design.webp
importance: -1
category: work
giscus_comments: true
---

Canada Visa Form Extraction (CVFE) allows you to convert Adobe protected visa application forms for Canadian Immigration into standard tabular data format, through RESTful API. The output can be used to create data analysis dashboards for better business insights, or automated decision making via predictive machine learning models. Also, many heuristics for feature engineering, data transformation, and standardization have been adopted by utilizing the experts' domain knowledge.

This tool has been used as part of the data ETL pipeline for systematically converting analog data into digitally structured data in large scale.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/cvfe-design.webp" title="CVFE design" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    CVFE design
</div>

<ul>
    <li>
        Source code is available on GitHub repo <a href="https://github.com/Nikronic/canada-visa-form-extraction">Nikronic/canada-visa-form-extraction</a>.
    </li>
    <li>
        You can find the documentation on <a href="https://nikronic.com/canada-visa-form-extraction">nikronic.com/canada-visa-form-extraction</a>
    </li>
    <li>
        Also available on <a href="https://pypi.org/project/cvfe/">PYPI/CVFE</a> which can be installed via `pip install cvfe`
    </li>
</ul>
