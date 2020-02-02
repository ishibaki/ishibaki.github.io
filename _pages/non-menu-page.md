---
permalink: /posts/
title: "Blog Posts"
author_profile: true
redirect_from: 
  - "/blog/"
  - "/blog.html"
---

# Blog Posts


{% include base_path %}

{% for post in site.posts reversed %}
  {% include archive-single.html %}
{% endfor %}
