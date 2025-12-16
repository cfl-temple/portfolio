---
title: "Home"
layout: homelay
excerpt: "CFL Lab at Temple University"
sitemap: false
permalink: /
---


<div class="jumbotron" style="background-color: #f8f9fa; padding: 40px 30px; margin-bottom: 30px;">
  <h1 style="margin-top: 0;">Welcome to CFL</h1>
  <p class="lead">We are a research group at Temple University focused on focused on robust and secure data fusion in distributed systems.</p>
  <p>Our mission is to advance the state of the art in distributed system decision fusion through innovative research and collaboration.</p>
  <p>
    <a class="btn btn-primary btn-lg" href="{{ site.baseurl }}/research" role="button">Learn more about our research</a>
  </p>
</div>

<div class="row">
  <div class="col-sm-8">
    <h2>About the Lab</h2>
    <p>Welcome to CFL. We are a research group at Temple University focused on robust and secure data fusion in distributed systems</p>
    
    <p>Our research interests include:</p>
    <ul>
    <li> Large Language Models (LLMs) for reasoning and adaptive decision-making.</li>
<li> Retrieval-Augmented Generation (RAG) for dynamic knowledge access.</li>
<li> Robotics and autonomous platforms for real-world sensing and actuation.</li>
<li> Edge and cloud computing architectures for scalable deployment.</li>
    </ul>
    
    <p>We are tackling a fundamental challenge: enabling robust and secure data fusion in environments where traditional sensors are being replaced by intelligent computers, robotics, and AI-driven agents. As computing and AI technologies advance, integration becomes critical—not just at the algorithmic level but across heterogeneous systems.</p>
    
    <h3>Research Focus</h3>
    <p>Our work addresses fundamental challenges in:</p>
    <ul>
    <li>System interoperability between robotics, AI models, and legacy infrastructure.</li>
<li>Secure communication protocols for multi-agent collaboration.</li>
<li> Privacy-preserving data fusion across distributed environments.</li>
<li>Real-time consensus and reliability in mission-critical applications.</li>
<li>Federated learning and multi-party computation for collaborative intelligence.</li>
    </ul>
    
    <p>Our goal is to create end-to-end integration systems that allow intelligent agents—whether robots, sensors, or AI models—to work together seamlessly, securely, and efficiently in complex environments.</p>
  </div>
  
  <div class="col-sm-4">
    <h2>News & Updates</h2>
    <div class="panel panel-default">
      <div class="panel-body">
        <h4>Latest News</h4>
        <ul class="list-unstyled">
          {% for news in site.data.news limit:5 %}
          <li style="margin-bottom: 15px;">
            <strong>{{ news.date }}</strong><br>
            {{ news.headline }}
          </li>
          {% endfor %}
        </ul>
        <a href="{{ site.baseurl }}/news" class="btn btn-sm btn-default">View all news</a>
      </div>
    </div>
    
    <h3>Quick Links</h3>
    <div class="list-group">
      <a href="{{ site.baseurl }}/team" class="list-group-item">
        <span class="glyphicon glyphicon-user"></span> Meet Our Team
      </a>
      <a href="{{ site.baseurl }}/publications" class="list-group-item">
        <span class="glyphicon glyphicon-book"></span> Publications
      </a>
      <a href="{{ site.baseurl }}/software" class="list-group-item">
        <span class="glyphicon glyphicon-download-alt"></span> Software & Tools
      </a>
      <a href="{{ site.baseurl }}/openings" class="list-group-item">
        <span class="glyphicon glyphicon-briefcase"></span> Join Us
      </a>
    </div>
  </div>
</div>
