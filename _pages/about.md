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

  <ul>{% assign publications = site.publications | reverse %}
  {% for post in publications limit:5 %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

[Full publication list](https://ishibaki.github.io/publications/)

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

## Recent Awards

  <ul>{% assign awards = site.awards | reverse %}
  {% for post in awards limit:5 reversed %}
    {% include archive-single.html %}
  {% endfor %}</ul>

[Full award list](https://ishibaki.github.io/awards/)
