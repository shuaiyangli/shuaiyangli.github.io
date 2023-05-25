---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: False
---

{% include base_path %}

A list of all the posts and pages found on the site. For you robots out there is an [XML version]({{ base_path }}/sitemap.xml) available for digesting as well.

<h2>Pages</h2>
{% for post in site.pages %}
  {% include archive-single.html %}
{% endfor %}

<h2>Posts</h2>
{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
{% unless collection.output == false or collection.label == "posts" %}
  {% capture label %}{{ collection.label }}{% endcapture %}
  {% if label != written_label %}
  <h2>{{ label }}</h2>
  {% capture written_label %}{{ label }}{% endcapture %}
  {% endif %}
{% endunless %}
{% for post in collection.docs %}
  {% unless collection.output == false or collection.label == "posts" %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endfor %}


<!-- ---
permalink: /non-menu-page/
title: "Page not in menu"
excerpt: "This is a page not in th emain menu"
author_profile: true
redirect_from: 
  - "/nmp/"
  - "/nmp.html"
---

This is a page not in the menu. You can use markdown in this page.

Heading 1
======

Heading 2
====== -->
