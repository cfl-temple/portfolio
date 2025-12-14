---
title: "Research"
layout: default
excerpt: "CFL Lab -- Research"
sitemap: false
permalink: /research/
---

<h1>Research</h1>

<p>We aim to address a fundamental challenge: solving diverse data fusion problems in an era where traditional sensors are gradually being replaced by intelligent computers and robotics. As computing advances, these intelligent agents introduce new complexities in data fusion. Our mission to investigate all research issues that arise in this context, including:</p>

<ul>
  <li>Security</li>
  <li>Reliability</li>
  <li>Privacy</li>
  <li>Multi-party computation</li>
  <li>And other critical aspects of collaborative intelligence</li>
</ul>

<p>By tackling these foundational problems, we strive to enable robust, secure, and efficient fusion across distributed intelligent systems.</p>

<p>The Computer Fusion Laboratory (CFL) is part of Temple University's Electrical and Computer Engineering Department under the leadership of Dr. Li Bai. The CFL pursues research in various areas of engineering including autonomous vehicle driving, distributed sensing and computing, multi-agent systems, wireless sensor networks, augmented reality and more. The think tank style laboratory explores what makes our world tick.</p>

<hr>

<h2>Research Projects</h2>

<!-- Search and Filter -->
<div style="margin: 20px 0;">
  <div class="row">
    <div class="col-md-6">
      <input type="text" id="project-search" class="form-control" placeholder="Search projects by title, description, or team member...">
    </div>
    <div class="col-md-6">
      <select id="category-filter" class="form-control">
        <option value="">All Categories</option>
        <option value="AI/ML">AI/ML</option>
        <option value="Cryptography">Cryptography</option>
        <option value="Data Analytics">Data Analytics</option>
        <option value="Distributed Systems">Distributed Systems</option>
        <option value="Healthcare">Healthcare</option>
        <option value="IoT">IoT</option>
        <option value="Mobile Computing">Mobile Computing</option>
        <option value="Robotics">Robotics</option>
        <option value="Security">Security</option>
        <option value="Software">Software</option>
        <option value="Wireless Networks">Wireless Networks</option>
      </select>
    </div>
  </div>
</div>

{% assign all_projects = "" | split: "" %}
{% for p in site.pages %}
  {% if p.path contains '_pages/research/' and p.order %}
    {% assign all_projects = all_projects | push: p %}
  {% endif %}
{% endfor %}
{% assign all_projects = all_projects | sort: 'order' | reverse %}

<!-- Recent 3 Projects (expanded) -->
{% assign count = 0 %}
{% for project in all_projects %}
{% if count < 3 %}
{% assign count = count | plus: 1 %}

<div class="project-item" data-title="{{ project.title | downcase }}" data-content="{{ project.content | strip_html | downcase }}" data-categories="{% for cat in project.categories %}{{ cat | downcase }} {% endfor %}" data-team="{% for member in project.team %}{{ member.name | downcase }} {% endfor %}">
<h3>{{ project.title }}</h3>
{% if project.years %}<p class="text-muted"><em>{{ project.years }}</em></p>{% endif %}
{% if project.categories %}
<p>
{% for cat in project.categories %}
<span class="label label-primary" style="margin-right: 5px;">{{ cat }}</span>
{% endfor %}
</p>
{% endif %}

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

<hr>
</div>

{% endif %}
{% endfor %}

<!-- Older Projects (collapsed) -->
{% assign older_count = all_projects | size | minus: 3 %}

{% if older_count > 0 %}

<div class="panel panel-default" style="margin-top: 20px;">
  <div class="panel-heading">
    <h4 class="panel-title">
      <a data-toggle="collapse" href="#older-projects" style="color: inherit;">
        <span class="glyphicon glyphicon-chevron-down"></span> More Projects
      </a>
    </h4>
  </div>
  <div id="older-projects" class="panel-collapse collapse">
    <div class="panel-body">
{% assign count2 = 0 %}
{% for project in all_projects %}
{% assign count2 = count2 | plus: 1 %}
{% if count2 > 3 %}
      <h3>{{ project.title }}</h3>
      {% if project.years %}<p class="text-muted"><em>{{ project.years }}</em></p>{% endif %}
      {% if project.categories %}
      <p>
      {% for cat in project.categories %}
      <span class="label label-primary" style="margin-right: 5px;">{{ cat }}</span>
      {% endfor %}
      </p>
      {% endif %}
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
      <hr>
{% endif %}
{% endfor %}
    </div>
  </div>
</div>

{% endif %}


<script>
document.addEventListener('DOMContentLoaded', function() {
  var searchInput = document.getElementById('project-search');
  var categoryFilter = document.getElementById('category-filter');
  var projectItems = document.querySelectorAll('.project-item');
  
  function filterProjects() {
    var searchTerm = searchInput.value.toLowerCase().trim();
    var selectedCategory = categoryFilter.value.toLowerCase();
    
    projectItems.forEach(function(item) {
      var title = item.getAttribute('data-title') || '';
      var content = item.getAttribute('data-content') || '';
      var categories = item.getAttribute('data-categories') || '';
      var team = item.getAttribute('data-team') || '';
      
      var matchesSearch = !searchTerm || 
        title.indexOf(searchTerm) !== -1 || 
        content.indexOf(searchTerm) !== -1 ||
        team.indexOf(searchTerm) !== -1;
      
      var matchesCategory = !selectedCategory || 
        categories.indexOf(selectedCategory) !== -1;
      
      if (matchesSearch && matchesCategory) {
        item.style.display = '';
      } else {
        item.style.display = 'none';
      }
    });
  }
  
  searchInput.addEventListener('input', filterProjects);
  categoryFilter.addEventListener('change', filterProjects);
});
</script>
