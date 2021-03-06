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

# Education

- Ph.D, Department of Biological Sciences, Osaka University, March 25th, 2019
- MS, Department of Biological Sciences, Osaka University, March 28th, 2016
- BS, Department of Biological Sciences, Osaka University, March 25th, 2014

# Work experience

- 2021-Today: Postdoctoral Researcher
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

# Skills

- Skills in *Drosophila melanogaster*
  - Developmental biology
  - Genetics
  - Cell biology
  - Molecular biology
- Bioinformatics
  - RNA-seq
  - Wholo genome sequencing
  - ChIP-seq

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
