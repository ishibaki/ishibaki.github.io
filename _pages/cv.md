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
    <a href="{{ edu.certification | prepend: "/images/" | prepend: base_path }}" class="image-popup">{{ edu.title }}</a>
  {% else %}
    {{ edu.title }}
  {% endif %}
, {{ edu.venue }}, {{ edu.date | default: "1900-01-01" | date: '%b %d, %Y' }}</li>
{% endfor %}</ul>

<!--
- [Ph.D.](../images/学位記.jpg), Department of Biological Sciences, Osaka University, March 25th, 2019
- MS, Department of Biological Sciences, Osaka University, March 28th, 2016
- BS, Department of Biological Sciences, Osaka University, March 25th, 2014
-->

# Research Experiences

<ul>{% for exp in site.experiences reversed %}
  <li>
  {% if exp.end %}
    {{ exp.start | date: '%Y' }} - {{ exp.end | date: '%Y' }}: 
  {% else %}
    {{ exp.start | date: '%Y' }} - Today: 
  {% endif %}
  {% if exp.certification %}
    <a href="{{ exp.certification }}">{{ exp.title }}</a>
  {% else %}
    {{ exp.title }}
  {% endif %}
  <ul>
    {% if exp.misc %}
      <li> {{ exp.misc }} </li>
    {% endif %}
    {% if exp.venueurl %}
      <li><a href="{{ exp.venueurl }}">{{ exp.venue }}</a></li>
    {% else %}
      <li>{{ exp.venue }}</li>
    {% endif %}
    {% if exp.superviser %}
      <li>Supervisor: {{ exp.superviser }}</li>
    {% endif %}
  </ul>
</li>
{% endfor %}</ul>

<!--
- 2022-Today: Postdoctoral Fellow (PD), Research Fellowship for Young Scientists, JSPS
  - Also as a Visiting Scientist
  - [Laboratory for Physical Biology](http://www.qbic.riken.jp/phb/), RIKEN BDR, Japan.
  - Supervisor: Dr. Tatsuo Shibata


- 2021-2022: Postdoctoral Researcher
  - [Laboratory for Physical Biology](http://www.qbic.riken.jp/phb/), RIKEN BDR, Japan.
  - Supervisor: Dr. Tatsuo Shibata

- 2019-2021: Postdoctoral Researcher
  - [Laboratory of Insect Ecology](http://www.insecteco.kais.kyoto-u.ac.jp/englishpage.html), Faulty of Agriculture, Kyoto University
  - Supervisor: Prof. Kenji Matsuura

- 2016-2019: [Research Fellowship for Young Scientists (DC1), JSPS](https://kaken.nii.ac.jp/en/grant/KAKENHI-PROJECT-16J01027/)
  - [Laboratory of Cell Biology](http://www.bio.sci.osaka-u.ac.jp/bio_web/lab_page/matsuno/Etop.html), Department of Biological Sciences, Osaka University
  - Supervisor: Prof. Kenji Matsuno

- 2011-2012: Lab technician
  - Laboratory of Genome and Chromosome Functions, Institute for Protein Research, Osaka University
  - Supervisor: Prof. Akira Shinohara
-->

# Publications

Total: {{ site.publications | size }}

  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

# Awards

Total: {{ site.awards | size }}

  <ul>{% for post in site.awards reversed %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

# Grants

Total: {{ site.grants | size }}

  <ul>{% for post in site.grants reversed %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

# Talks

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
