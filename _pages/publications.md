---
layout: page
permalink: /publications/
title: Publications
description: 
years: [2024, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015]
nav: true
nav_order: 3
---


<!-- _pages/publications.md -->
<div class="publications">
<p>For the most up-to-date list of publications, please refer to <a href="https://scholar.google.com/citations?user=2QsddMIAAAAJ&hl=en">Google Scholar</a>.</p>


{% capture num_per_year %}
{% bibliography_count --file preprints %}
{% endcapture %}
{% if num_per_year contains "0" %}  
{% else %}
    {% capture numPapers %}
    {% bibliography_count --file preprints --group_order descending %}
    {% endcapture %}
    <h1 class="publications">Preprints</h1>
    <h1 class="bibliography" style="counter-reset:bibitem {{numPapers|plus:1}}"></h1>
    <h2 class="year">&nbsp;</h2>
    {% for y in page.years %} 
      {% bibliography --file preprints -q @*[year={{y}}]* %}
    {% endfor %}
{% endif %}  


<h1 class="publications">Journal Articles</h1>
{% capture numPapers %}
{% bibliography_count --file papers --group_order descending %}
{% endcapture %}
<h1 class="bibliography" style="counter-reset:bibitem {{numPapers|plus:1}}"></h1>

{% for y in page.years %}
  {% capture num_per_year %}
  {% bibliography_count --file papers --group_order descending -q @*[year={{y}}]* %}
  {% endcapture %}
  {% if num_per_year contains "0" %}
  {% else %}
    <h2 class="year">{{y}}</h2>
    {% bibliography -q @*[year={{y}}]* %}
  {% endif %}
{% endfor %}



</div>
