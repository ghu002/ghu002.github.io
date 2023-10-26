---
layout: page
permalink: /group/
title: Group 
description: 
nav: true
nav_order: 2
---


<div class="group">  
<h5><a href="../openings">We are currently looking for undergraduate/graduate/postdoctoral students to join us! (8/1/2023)</a></h5>

<h2>PI</h2>

<div class="row" id="PI">
  <div class="col-sm-6"> 
    <img src="{{ site.url }}{{ site.baseurl }}/assets/img/Emma_2.PNG"/>
  </div>
  <div class="col-sm-6" style="text-align:left"> 
    <h4> {{ site.first_name }} {{ site.middle_name }} {{ site.last_name }} </h4>
    <h5> {{ site.position }} </h5>
    <p style="text-align:justify"> Dr. Hu joined the School of MSE at Georgia Tech as an Assistant Professor in Fall 2023. Prior to this position, she was an Assistant Professor at City University of New York from 2020-2023. She was a postdoctoral scholar in the Center for Nanophase Materials Sciences at Oak Ridge National Laboratory from 2018-2020. She obtained her Ph.D. in Physical Chemistry in 2018 from the University of California, Riverside, and her B.S. in Chemistry in 2013 from University of Science and Technology of China. Dr. Hu develops and applies advanced computational methods to study earth-abundant and environment friendly materials for energy and electronic applications.  
    </p>
    {%- if site.cv -%} <a href="{{ site.url }}{{ site.baseurl }}/assets/pdf/CV.pdf" title="CV"><i class="ai ai-cv ai-2x"></i></a> {% endif %}   
    {%- if site.email -%} <a href="mailto:{{ site.email | encode_email }}" title="Email"><i class="fas fa-envelope-square ai-2x"></i></a> {% endif %}       
    {%- if site.scholar_userid -%} <a href="https://scholar.google.com/citations?user={{ site.scholar_userid }}" title="Google Scholar"><i class="ai ai-google-scholar ai-2x"></i></a> {% endif %}                                
    {%- if site.orcid_id -%} <a href="https://orcid.org/{{ site.orcid_id }}" title="ORCID"><i class="ai ai-orcid ai-2x"></i></a> {% endif %}
    {%- if site.research_gate_profile -%} <a href="https://www.researchgate.net/profile/{{site.research_gate_profile}}/" title="ResearchGate"><i class="ai ai-researchgate ai-2x"></i></a> {% endif %}
    {%- if site.linkedin_username -%} <a href="https://www.linkedin.com/in/{{ site.linkedin_username }}" title="LinkedIn"><i class="fab fa-linkedin ai-2x"></i></a> {% endif %}
                        
  </div>  
</div>

<h2>Team</h2>

{% assign number_printed = 0 %} 
{% for coauthor in site.data.coauthors %}
  
  {% if coauthor.alumni == false and coauthor.visible == true %}
  
    {% assign even_odd = number_printed | modulo: 2 %}
    
    {% if even_odd == 0 %}
      <div class="row">
    {% endif %}
    
    <div class="col-sm-1">
    </div>    
    <div class="col-sm-2">
      <img src="{{ site.url }}{{ site.baseurl }}/assets/img/{{ coauthor.photo }}"/>
    </div>
    <div class="col-sm-3"> 
      <h5>{{ coauthor.firstname }} {{ coauthor.lastname }}</h5>
      <h5><i>{{ coauthor.position }}</i><br></h5>
      {% if coauthor.cv %} <a href="{{ site.url }}{{ site.baseurl }}/assets/pdf/{{ coauthor.cv }}" title="CV"><i class="ai ai-cv ai-2x"></i></a> {% endif %}   
      {% if coauthor.email %}<a href="mailto:{{ coauthor.email }}" title="Email"><i class="fa fa-envelope-square fa-2x"></i></a> {% endif %} 
      {% if coauthor.scholar %} <a href="{{ coauthor.scholar }}" title="Google Scholar"><i class="ai ai-google-scholar ai-2x"></i></a> {% endif %}  
      {% if coauthor.website %} <a href="{{ coauthor.website }}" title="Website"><i class="fa fa-home fa-2x"></i></a> {% endif %}          

    </div>
    
    {% assign number_printed = number_printed | plus: 1 %}
    
    {% if even_odd == 1 %} 
      </div>
    {% endif %}
  
  {% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
  </div>
{% endif %}


<h2>Alumni</h2> 

<ul>
{% for coauthor in site.data.coauthors %}
  
  {% if coauthor.alumni == true  and coauthor.visible == true %}
    <li>
    {{ coauthor.firstname }} {{ coauthor.lastname | append : ',' }}
    {% if coauthor.position %}<i>{{ coauthor.position | append : ',' }}</i>{% endif %} 
    {% if coauthor.email %}<a href="mailto:{{ coauthor.email }}" target="Email"><i class="fas fa-envelope-square fa-1x"></i></a> {% endif %} 
    {% if coauthor.website %} <a href="{{ coauthor.website }}" target="Website"><i class="fa fa-home fa-1x"></i></a> {% endif %}   
    </li>
  {% endif %}

{% endfor %}
</ul>

</div>
