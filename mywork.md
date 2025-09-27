---
layout: archive
intro: 
  - excerpt: 'Nullam suscipit et nam, tellus velit pellentesque at malesuada, enim eaque. Quis nulla, netus tempor in diam gravida tincidunt, *proin faucibus* voluptate felis id sollicitudin. Centered with `type="center"`'
---

{{ content }}

<h3 class="archive__subtitle">{{ site.data.ui-text[site.locale].recent_posts | default: "Recent Posts" }}</h3>

{% if paginator %}
  {% assign posts = paginator.posts %}
{% else %}
  {% assign posts = site.posts %}
{% endif %}

{% assign entries_layout = page.entries_layout | default: 'grid' %}
<div class="entries-{{ entries_layout }}">
    {% for post in posts %}
        {% if post.highlight_home and post.categories contains "work" %}  
        {% include archive-single.html type=entries_layout %}
        {% endif %}
    {% endfor %} 

</div>

{% include paginator.html %}
