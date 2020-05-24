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

- BS, Department of Biological Sciences, Osaka University, March 25th, 2014
- MS, Department of Biological Sciences, Osaka University, March 28th, 2016
- Ph.D, Department of Biological Sciences, Osaka University, March 25th, 2019

# Work experience

- 2011-2012: Lab technician
  - Laboratory of Genome and Chromosome Functions, Institute for Protein Research, Osaka University
  - Supervisor: Prof. Akira Shinohara

- 2016-2019: [Research Fellowship for Young Scientists (DC1), JSPS](https://kaken.nii.ac.jp/en/grant/KAKENHI-PROJECT-16J01027/)
  - [Laboratory of Cell Biology](http://www.bio.sci.osaka-u.ac.jp/bio_web/lab_page/matsuno/Etop.html), Department of Biological Sciences, Osaka University
  - Supervisor: Prof. Kenji Matsuno

- 2019-Today: Postdoctoral Researcher
  - [Laboratory of Insect Ecology](http://www.insecteco.kais.kyoto-u.ac.jp/englishpage.html), Faulty of Agriculture, Kyoto University
  - Supervisor: Prof. Kenji Matsuura

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

  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

# Awards

  <ul>{% for post in site.awards reversed %}
    {% include archive-single.html %}
  {% endfor %}</ul>

# Talks

  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

# Teaching

  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
