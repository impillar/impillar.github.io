---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a></u> or <u><a href="{{author.dblp}}">DBLP</a></u>
{% endif %}

  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a></u> or <u><a href="{{author.dblp}}">DBLP</a></u>

{% for post in site.publications reversed %}
  {% include archive-publication.html %}
{% endfor %}
