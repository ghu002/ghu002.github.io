---
layout: page
title: Research
permalink: /research/
description:
nav: true
nav_order: 1
display_categories: [research1]
horizontal: false
---


<div class="jumbotron projects">
<h4>Electrochemical catalysis</h4>
<p style="text-align:justify">
One major challenge shared in the development of water splitting devices, regenerative fuel cells, and rechargeable metal-air batteries is finding suitable materials that can efficiently and stably catalyze the key electrochemical processes involved. However, an atomic scale understanding of the electrochemical interfaces and mechanisms of electron transfer and catalytic reactions at the interfaces remains limited. To address this problem, we develop and apply computational approaches based on density functional theory (DFT) and machine leaning (ML) to reveal the dynamic structure evolution of electrochemical interfaces under reaction conditions, and map out the reaction pathways of energy-related electrochemical reactions such as CO2RR, ORR, OER, and HER. 
</p>

<div class="row">
  <div class="col-sm-12" style="text-align:center">
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/Research_1.TIF" width="75%">
  </div>
</div>

</div>

<div class="jumbotron projects">
<h4>Neuromorphic computing</h4>
<p style="text-align:justify">
Neuromorphic computing is a new paradigm for computer architecture which mimic human brains, and is expected to be vastly more energy efficient than modern computers based on the von Neumann architecture. Strongly correlated quantum materials are considered to be ideal candidates for artificial neurons and synapses due to their pronounced non-linear properties through material phase transitions. However, standard DFT calculations struggle to treat such systems accurately due to large delocalization and self-interaction errors. Here we apply the many body quantum Monte Carlo (QMC) method to provide accurate predictions of structural, electronic, and magnetic properties of strongly correlated materials, and new insights into the mechanisms of their phase transitions.
</p>

<div class="row">
  <div class="col-sm-12" style="text-align:center">
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/Research_2.TIF" width="100%">
  </div>
</div>

</div>

<div class="jumbotron projects">
<h4>Light harvesting</h4>
<p style="text-align:justify">
Solar light harvesting is an attractive means of energy utilization to help solve our global energy needs without depleting natural resources. Halide perovskites are an emerging family of materials in this field owing to their low-costs, high photoluminescence quantum yields, and broadly tunable optical properties. However, they possess very ionic surfaces capped with weakly bound and highly dynamic surface ligands, which presents significant issues for long-term stability. We use computational high-throughput screening (HTS) to search for ligands which provide effective passivation for surface traps, and anchoring motifs which promote energy transfer across the inorganic/organic interface.  
</p>

<div class="row">
  <div class="col-sm-12" style="text-align:center">
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/Research_3.TIF" width="100%">
  </div>
</div>

</div>

<div class="jumbotron projects">
<h4>Functional 2D materials</h4>
<p style="text-align:justify">
The edges of 2D materials, analogous to surfaces of bulk materials, exhibit unique properties from their basal plane. In addition to the pristine zigzag or armchair edges common to hexagonal 2D materials, reconstructed edges have many possible structures with significantly different electronic and magnetic properties. This could give rise to a wide continuum of functionalities which can be tuned by controlled synthesis. However, the whole chemical space of synthesizable reconstructed edges, and their functional properties remain poorly understood. In addition, currently no clear approach exists to provide actionable experimental guidance to synthesize the desired edges. We therefore develop computational frameworks to rapidly and efficiently predict synthesizable reconstructed edges in 2D materials, and collaborate with experimental groups to enable the closed-loop synthesis of these edges.  
</p>

<div class="row">
  <div class="col-sm-12" style="text-align:center">
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/Research_34.TIF" width="100%">
  </div>
</div>

</div>

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{  }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %} 
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
