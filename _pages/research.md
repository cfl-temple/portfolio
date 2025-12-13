---
title: "Research"
layout: default
excerpt: "CFL Lab -- Research"
sitemap: false
permalink: /research/
---

# Research

We aim to address a fundamental challenge: solving diverse data fusion problems in an era where traditional sensors are gradually being replaced by intelligent computers and robotics. As computing advances, these intelligent agents introduce new complexities in data fusion. Our mission is to investigate all research issues that arise in this context, including:

- Security
- Reliability
- Privacy
- Multi-party computation,
- And other critical aspects of collaborative intelligence.

By tackling these foundational problems, we strive to enable robust, secure, and efficient fusion across distributed intelligent systems.

The Computer Fusion Laboratory (CFL) is part of Temple University's Electrical and Computer Engineering Department under the leadership of Dr. Li Bai. The CFL pursues research in various areas of engineering including autonomous vehicle driving, distributed sensing and computing, multi-agent systems, wireless sensor networks, augmented reality and more. The think tank style laboratory explores what makes our world tick.

---

## Research Projects

{% assign all_pages = site.pages | sort: 'order' %}

<!-- Recent 3 Projects (expanded) -->
{% for project in all_pages %}
{% if project.path contains '_pages/research/' and project.order and project.order <= 3 %}

### {{ project.title }}
{% if project.years %}<p class="text-muted"><em>{{ project.years }}</em></p>{% endif %}

<div class="research">
{% if project.image %}
<img src="{{ site.baseurl }}/images/research/{{ project.image }}" style="max-width: 400px; float: right; margin-left: 20px;">
{% endif %}
</div>

{{ project.content }}

{% if project.team %}
<h4>Team Members</h4>
<ul>
{% for member in project.team %}
  <li><strong>{{ member.name }}</strong> - {{ member.role }}</li>
{% endfor %}
</ul>
{% endif %}

<div style="clear: both;"></div>

---

{% endif %}
{% endfor %}

<!-- Older Projects (collapsed) -->
{% assign has_older = false %}
{% for project in all_pages %}
  {% if project.path contains '_pages/research/' and project.order and project.order > 3 %}
    {% assign has_older = true %}
  {% endif %}
{% endfor %}

{% if has_older %}

<div class="panel panel-default" style="margin-top: 20px;">
  <div class="panel-heading">
    <h4 class="panel-title">
      <a data-toggle="collapse" href="#older-projects" style="color: inherit;">
        <span class="glyphicon glyphicon-chevron-down"></span> More Projects
      </a>
    </h4>
  </div>
  <div id="older-projects" class="panel-collapse collapse">
    <div class="panel-body" markdown="0">
{% for project in all_pages %}{% if project.path contains '_pages/research/' and project.order and project.order > 3 %}
      <h3>{{ project.title }}</h3>
      {% if project.years %}<p class="text-muted"><em>{{ project.years }}</em></p>{% endif %}
      <div class="research">{% if project.image %}<img src="{{ site.baseurl }}/images/research/{{ project.image }}" style="max-width: 400px; float: right; margin-left: 20px;">{% endif %}</div>
      <div>{{ project.content }}</div>
      {% if project.team %}<h4>Team Members</h4><ul>{% for member in project.team %}<li><strong>{{ member.name }}</strong> - {{ member.role }}</li>{% endfor %}</ul>{% endif %}
      <div style="clear: both;"></div>
      <hr>
{% endif %}{% endfor %}
    </div>
  </div>
</div>

{% endif %}
