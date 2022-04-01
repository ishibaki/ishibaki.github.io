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
<!-- {% include mermaid.html %} -->

```mermaid
gantt
section Education
  Bachelor : BS, 2010-04-01, 2014-03-25
  Master   : MS, 2014-04-01, 2016-03-28
  Ph.D.    : Ph.D., 2016-04-01, 2019-03-25
section Work experience
  Lab tech.@Osaka Univ.  : OU-tech, 2011-04-01, 2012-03-31
  JSPS DC1 @Osaka Univ.  : DC1, 2016-04-01, 2019-03-31
  Post-doc @Kyoto Univ.  : KU-postdoc, after DC1, 2021-04-30
  Post-doc @RIKEN        : RIKEN-postdoc, after KU-postdoc, 2022-03-31
  JSPS PD @RIKEN         : active, PD, after RIKEN-postdoc, 2025-03-31
```

# Education

- [Ph.D.](../images/学位記.jpg), Department of Biological Sciences, Osaka University, March 25th, 2019
- MS, Department of Biological Sciences, Osaka University, March 28th, 2016
- BS, Department of Biological Sciences, Osaka University, March 25th, 2014

# Work experience

- 2022-Today: Postdoctoral Fellow (PD), Research Fellowship for Young Scientists, JSPS
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

# Skills

- Skills in *Drosophila melanogaster*
  - Developmental biology
  - Genetics
  - Cell biology
  - Molecular biology
- Bioinformatics
  - RNA-seq
  - Whole genome sequencing
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
