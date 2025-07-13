---
layout: page
title: AI Expert-in-a-Box
description: A framework for any organization that has domain-specific enterprize unstructured data where internal experts need to automate complex decision-making.
img: assets/img/vizard-teaser-ai-generated.webp
importance: -1
category: work
giscus_comments: true
# github: https://github.com/Nikronic/wizard
---

<!-- Intro section -->
<section>
<h2>Overview</h2>
<p>
    This is a powerful framework for building AI-powered <em>Decision Support Systems</em>. It transforms messy, domain-specific, enterprize data into structured, explainable predictions, helping experts make consistent, data-driven decisions.
</p>
</section>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/vizard-teaser-ai-generated.webp" title="Vizard Overview" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Vizard Overview
</div>

<em>PS:</em> Unfortunately I failed at finalizing and commercializing it; <a href="https://instabase.com/">Instabase</a> startup successfully released a closely resembling concept, as an <em>AI-Native Unstructured Data Platform</em>. Congrats to them! :)


<!-- Section: Summary for General Audience -->
<section>
  <h3>General Summary</h3>

  <h4>What is this project?</h4>
  <p>Vizard is a powerful and flexible framework for building specialized "Decision Support Systems." It is designed to take complex, often non-standard company data (like proprietary forms, technical logs, or design files), understand it, and then use AI to make intelligent predictions and provide clear explanations. Think of it as an "AI expert-in-a-box" that can be tailored to very specific business problems.</p>

  <h4>Who is it for?</h4>
  <p>This framework is for any organization that has unique, domain-specific data and needs to automate complex decision-making. The target users are internal experts (like engineers, analysts, or case managers) who need AI-powered assistance to evaluate items, assess risk, or predict outcomes quickly and consistently.</p>

  <h4>Core problem solved</h4>
  <p>In many industries, decision-making relies on the intuition of a few senior experts who can interpret complex, unstructured data. This process is slow, difficult to scale, and subjective. Vizard solves this by capturing that expert knowledge in a structured, repeatable AI system. It turns proprietary data into a competitive advantage by enabling consistent, data-driven, and transparent decisions across an entire team.</p>

  <h4>Key Features</h4>
  <ul>
    <li><strong>Specialized Data Ingestion:</strong>The system is built to handle data that doesn't fit into simple spreadsheets. It has a pipeline to extract meaningful information from complex formats, such as protected industry-specific forms or structured files.</li>
    <li><strong>Expert Knowledge Integration:</strong>Vizard's core strength is its ability to be "taught" using expert rules of thumb. If you have a large dataset but only a few confirmed outcomes, the system can use these rules to intelligently label the rest of the data, dramatically accelerating AI model training.</li>
    <li><strong>Explainable Predictions:</strong>The system doesn’t just give an answer (e.g., "75% risk"); it explains why. It highlights the specific data points that most influenced its conclusion, allowing users to trust the result and take targeted action.</li>
    <li><strong>Hybrid Intelligence:</strong>The platform allows for manual, expert-driven adjustments to the AI's prediction. This means an expert can override or fine-tune the final score based on information the model might have missed, combining the best of machine intelligence and human intuition.</li>

  </ul>

  <h4>Potential Application Areas</h4>
  This architecture is highly effective for problems with the following characteristics: (1) complex/proprietary input data, (2) limited ground-truth labels, and (3) a need for explainable and auditable decisions.

  <ul>
    <ul>
        <li><strong>Example of Additive Manufacturing (CAD Analysis)</strong></li>
    <ul>
      <li><strong>Problem</strong>: Predict the manufacturability, cost, or stress-failure risk of a 3D-printed part from its CAD file.</li>
      <li><strong>Mapping to Vizard's Architecture:</strong></li>
      <ul>
        <li>`data/`: Ingest .stl or .step files. Extract geometric features (volume, surface area, overhang angles, wall thickness).</li>
        <li>`snorkel/`: Use engineering heuristics as LabelingFunctions (e.g., if overhang_angle > 45: return WEAK_FAIL). Programmatically label thousands of designs.</li>
        <li>`xai/`: Explain why a part is predicted to fail (e.g., "High SHAP value for 'thin_wall_feature'").</li>
      </ul>
    </ul>

    <li><strong>Example of Insurance Claim Adjudication</strong></li>
    <ul>
      <li><strong>Problem</strong>: Predict the likelihood of a submitted insurance claim being fraudulent.</li>
      <li><strong>Mapping to Vizard's Architecture:</strong></li>
      <ul>
        <li>`data/`: Ingest complex claim forms (PDFs with text, tables, and images). Use OCR and layout analysis to extract structured data.</li>
        <li>`snorkel/`: Use adjuster's rules as LabelingFunctions (e.g., if multiple_claims_in_30_days: return WEAK_FRAUD)</li>
        <li>`estimators/manual/`: Allow a senior adjuster to manually boost the fraud score if they have external information not captured in the form.</li>
      </ul>
    </ul>
    </ul>
  </ul>
</section>

<section>
  <h3>Future Potential with Foundation Models</h3>
  The Vizard architecture is primed for enhancement with Foundation Models (LLMs). Its modularity and focus on structured, explainable outputs make it a perfect "tool" for an LLM to use.

  <h4>Generative Interface for Complex Querying & "What-If" Analysis</h4>
  <ul>
    <li></strong>Feature:</strong>Create a natural language interface that allows experts to query the system and run simulations without writing code or filling out forms. For example, a design engineer could ask: "What would be the effect on the manufacturability score if I increase the wall thickness of this part from 2mm to 3mm but switch the material to ABS?"</li>
    <li><strong>User Benefit:</strong>This moves the tool from a static evaluator to a dynamic creative partner. It drastically lowers the barrier to exploring complex trade-offs and allows for rapid, iterative design and risk assessment.</li>
    <li><strong>Technical Outline:</strong></li>
    <ul>
      <li>Use an LLM with strong function-calling/tool-use capabilities (e.g. Gemini).</li>
      <li>The LLM would be the conversational front-end. It would parse the user's natural language query.</li>
      <li>It would identify the variables to change and generate multiple JSON payloads for the existing /predict and /xai endpoints</li>
      <li>The LLM would then receive the structured JSON responses, compare them, and synthesize a comparative summary for the user (e.g., "Increasing the thickness to 3mm improves the structural score by 15%, but using ABS increases the predicted print time by 25 minutes.").</li>
    </ul>
  </ul>

  <h4> Multimodal Feature Extraction from Proprietary Data</h4>
  <ul>
    <li></strong>Feature:</strong>Directly process complex, non-textual data formats (like CAD files, medical images, or circuit diagrams) to extract high-level, conceptual features that the current pipeline cannot. For example, analyzing a CAD file to generate a feature called design_complexity ("simple," "moderate," "complex") or aesthetic_quality.</li>
    <li><strong>User Benefit:</strong>This unlocks a new dimension of understanding from the company's core data assets. The model can learn from subtle, qualitative aspects of the data that were previously only accessible to human experts.</li>
    <li><strong>Technical Outline:</strong></li>
    <ul>
      <li>Integrate a multimodal foundation model (e.g., GPT-4o, LLaVA).</li>
      <li>In the vizard/data pipeline, add a step where an image rendering of the proprietary data (e.g., a snapshot of a CAD model) is sent to the multimodal LLM.</li>
      <li>The prompt would ask the model to act as a domain expert: "As a mechanical engineer, describe the complexity of this part. Rate its manufacturability on a scale of 1-10 based on visual inspection. Is it more functional or aesthetic?"</li>
      <li>The LLM's structured response (e.g., {"complexity": "high", "visual_manufacturability": 3}) becomes new input features for the existing FLAML model, enriching its predictive power.</li>
    </ul>
  </ul>
</section>