---
layout: archive
title: "CV"
permalink: /cv/
description: 石橋朋樹の履歴書
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}
{% include toc %}
{% include mermaid-cv.md %}

# Education

<ul>{% for edu in site.education reversed %}
<li>
  {% if edu.certification %}
    <a href="{{ edu.certification | prepend: "/images/" | prepend: base_path }}" class="image-popup">{{ edu.title }}</a>, {{ edu.venue }}, {{ edu.date | default: "1900-01-01" | date: '%b %d, %Y' }}</li>
  {% else %}
    {{ edu.title }}, {{ edu.venue }}, {{ edu.date | default: "1900-01-01" | date: '%b %d, %Y' }}</li>
  {% endif %}
{% endfor %}</ul>

# Research Experiences

<ul>{% for exp in site.experiences reversed %}
  <li>
  {% if exp.end %}
    {{ exp.start | date: '%Y' }} - {{ exp.end | date: '%Y' }}: 
  {% else %}
    {{ exp.start | date: '%Y' }} - Today: 
  {% endif %}
  {% if exp.certification %}
    <a href="{{ exp.certification }}" target="_blank" rel="noopener noreferrer">{{ exp.title }}</a>
  {% else %}
    {{ exp.title }}
  {% endif %}
  <ul>
    {% if exp.misc %}
      <li> {{ exp.misc }} </li>
    {% endif %}
    {% if exp.venueurl %}
      <li><a href="{{ exp.venueurl }}" target="_blank" rel="noopener noreferrer">{{ exp.lab }}</a>, {{ exp.dept }}, {{ exp.institute }}, {{ exp.country }}</li>
    {% else %}
      <li>{{ exp.lab }}, {{ exp.dept }}, {{ exp.institute }}, {{ exp.country }}</li>
    {% endif %}
    {% if exp.superviser %}
      <li>Supervisor: {{ exp.superviser }}</li>
    {% endif %}
  </ul>
</li>
{% endfor %}</ul>

# Publications

{% assign peer_pubs = site.publications | where: "is_peer", true %}
Total: {{ site.publications | size }}, Peer-reviewed: {{ peer_pubs | size }}  

  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

- ◎ signs indicate peer reviewed papers.
- <sup>*</sup> signs indicate equally contributed authors.
- <sup>†</sup> signs indicate corresponding authors.

# Awards

Total: {{ site.awards | size }}

  <ul>{% for post in site.awards reversed %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

# Funding

Total: {{ site.grants | size }}

  <ul>{% for post in site.grants reversed %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

# Presentations

Total: {{ site.talks | size }}

  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

# Teaching

Total: {{ site.teaching | size }}

  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

# Skills

{% include skill-list.md %}
