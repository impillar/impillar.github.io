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

  You can also find my articles on <u><a href="https://scholar.google.com.sg/citations?user=fpE34K0AAAAJ&hl=en">my Google Scholar profile</a></u> or <u><a href="https://dblp.uni-trier.de/pers/hd/m/Meng:Guozhu">DBLP</a></u>

{% for post in site.publications reversed %}
  {% include archive-publication.html %}
{% endfor %}
