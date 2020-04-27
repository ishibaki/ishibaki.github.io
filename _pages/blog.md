---
permalink: /blog/
title: "Blog Posts"
author_profile: true
redirect_from: 
  - "/blog.html"
---

# ブログのようなもの

twitterで言うようなことじゃないけど，外部化しておきたいこと．

{% include base_path %}

{% for post in site.blog reversed %}
  {% include archive-single.html %}
{% endfor %}

---

いちおう，Githubアカウント持ってたらコメントできるようになってます．

<script src="https://utteranc.es/client.js"
        repo="ishibaki/ishibaki.github.io"
        issue-term="title"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
