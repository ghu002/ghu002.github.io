---
layout: page
permalink: /allnews/
title: News
description: 
nav: false
nav_order: 2
---

<div class="news">
  {% if site.news != blank -%} 
  <div class="table-responsive">
    <table class="table table-sm table-borderless">
    {%- assign news = site.news | reverse -%} 
    {% for item in news%} 
      {% if site.news != blank -%}  
        {% if item.visible == true %}
          <tr>
            <th scope="row">{{ item.date | date: "%b %-d, %Y" }}</th>
            <td>
              {% if item.inline -%} 
                {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
              {%- else -%} 
                <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
              {%- endif %} 
            </td>
          </tr>
        {%- endif %} 
      {%- endif %} 
    {%- endfor %} 
    </table>
  </div>
  {%- endif %}             
</div>
