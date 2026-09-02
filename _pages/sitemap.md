---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

A list of all the pages and posts found on this site. For you robots out there,
there is an [XML version]({{ base_path }}/sitemap.xml) available for digesting as
well.

<h2>Pages</h2>
{% for post in site.pages %}
  {% unless post.sitemap == false or post.title == nil or post.title == empty %}
    {% include archive-single.html %}
  {% endunless %}
{% endfor %}

{% if site.posts.size > 0 %}
<h2>Posts</h2>
{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}
{% endif %}

{% for collection in site.collections %}
  {% unless collection.output == false or collection.label == "posts" or collection.docs.size == 0 %}
  <h2>{{ collection.label | capitalize }}</h2>
  {% for post in collection.docs %}
    {% include archive-single.html %}
  {% endfor %}
  {% endunless %}
{% endfor %}
