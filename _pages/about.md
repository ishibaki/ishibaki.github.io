---
permalink: /
title: "Hello"
excerpt: "Hello"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

This is Tomoki Ishibashi's website.

I am now working as a Post-doc in [Matsuura Lab](http://www.insecteco.kais.kyoto-u.ac.jp/englishpage.html), Kyoto University, Japan.

Previously, I was a student in [Matsuno Lab](http://www.bio.sci.osaka-u.ac.jp/bio_web/lab_page/matsuno/Etop.html), Osaka University, Japan.

---

## Recent Publications

  <ul>{% for post in site.publications reversed limit:5 %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

---

## Skills

- Skills for *Drosophila melanogaster*
  - Developmental biology
  - Genetics
  - Cell biology
  - Molecular biology
  - Imaging
- Skills for termites
  - Ecology
  - Mathematical modeling
- Bioinformatics
  - RNA-seq
  - Whole genome sequencing
  - ChIP-seq

---

## Awards

  <ul>{% for post in site.awards reversed %}
    {% include archive-single.html %}
  {% endfor %}</ul>

