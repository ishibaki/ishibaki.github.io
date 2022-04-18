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

I am now working as a
{% for experience in site.experiences %}{% if experience.toplist %}{% assign exp = experience %}{% endif %}{% endfor %}{{ exp.abbrev }} in {{ exp.lab }}, {{ exp.institute }}, {{ exp.country }}.

Previously, I was  

<ul>{% for exp in site.experiences reversed %}
  {% if exp.done and exp.toplist %}
  <li>
    a {{ exp.abbrev }} in {{ exp.lab }}, {{ exp.institute }}, {{ exp.country }}
  </li>
  {% endif %}
{% endfor %}
</ul>

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

## Recent Publications (3 of {{ site.publications | size }})

  <ul>{% assign publications = site.publications | reverse %}
  {% for post in publications limit:3 %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

[Full publication list](https://ishibaki.github.io/cv/#publications)

---

## Recent Awards (3 of {{ site.awards | size }})

  <ul>{% assign awards = site.awards | reverse %}
  {% for post in awards limit:3 reversed %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

[Full award list](https://ishibaki.github.io/awards/)

---
  
## Recent Presentations (3 of {{ site.talks | size }})

  <ul>{% assign talks = site.talks | reverse %}
  {% for post in talks limit:3 reversed %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>

[Full presentation list](https://ishibaki.github.io/talks/)

---

## Skills

{% include skill-list.md %}

---

<font size="1" color="#fafafa">link to my blog: https://ishibaki.github.io/blog/</font>
