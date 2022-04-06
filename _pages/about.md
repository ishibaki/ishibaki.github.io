---
permalink: /
title: "Welcome!"
excerpt: "Hello"
description: 石橋朋樹のホームページです/This is Tomoki Ishibashi's website
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

This is Tomoki Ishibashi's website.

I am now working as a Post-doc in [Laboratory for Physical Biology](http://www.qbic.riken.jp/phb/), RIKEN BDR, Japan.

Previously, I was  
- a Post-doc in [Matsuura Lab](http://www.insecteco.kais.kyoto-u.ac.jp/englishpage.html), Kyoto University, Japan;
- a student in [Matsuno Lab](http://www.bio.sci.osaka-u.ac.jp/bio_web/lab_page/matsuno/Etop.html), Osaka University, Japan.

<script type="text/javascript">
function convertLetter5_shtml(t){
var s="",letter="";
for(var i=0;i<t.length;i++){
letter=t.charCodeAt(i);
s +=String.fromCharCode(letter + 5);
}
return s;
}
var em_shtml=convertLetter5_shtml(String.fromCharCode(111, 106, 104, 106, 102, 100, 41, 100, 110, 99, 100, 93, 92, 110, 99, 100)+String.fromCharCode(59, 109, 100, 102, 96, 105, 41, 101, 107));
document.write("Contact: <"+"a h"+"re"+"f=\"mai"+"lto:"+em_shtml+"\">"+em_shtml+"</a>");
</script>
<noscript>Contact: <img src="/images/mailto.png"></noscript>

---

## Recent Publications

  <ul>{% assign publications = site.publications | reverse %}
  {% for post in publications limit:3 %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

[Full publication list](https://ishibaki.github.io/cv/#publications)

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

---

## Recent Presentations

  <ul>{% assign talks = site.talks | reverse %}
  {% for post in talks limit:5 reversed %}
    {% include archive-single.html %}
  {% endfor %}</ul>

[Full presentation list](https://ishibaki.github.io/talks/)

---

<font size="1" color="#fafafa">link to my blog: https://ishibaki.github.io/blog/</font>
