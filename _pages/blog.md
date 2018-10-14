---
layout: posts
permalink: /blog/
title: "Blog"
author_profile: true
header:
  image: "https://www.atlanticbreeze.co.za/wp-content/uploads/2017/04/V-A-Waterfront.jpg"
---
{% include base_path %}
{% include group-by-array collection=site.posts field="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
