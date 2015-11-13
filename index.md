---
title: nEDM Experiment Documentation
layout: basic
---

## nEDM Experiment documentation

This page provides documentation for software and systems used in the neutron
electric dipole moment (nEDM) experiment located at the Technische Universität
München (FRM-II).

<h3 id="main-pages">Main pages</h3>
<ul>
{% for repo in site.repohash %}
  {% assign the_next_site = null %}
  {% for r in site.github.public_repositories %}
    {% if r.name == repo[0] %}
      {% assign the_next_site = r %}
      {% assign page_name = repo[1].name %}
      {% assign description = r.description %}
      {% if repo[1].description %}
        {% assign description = repo[1].description %}
      {% endif %}
      {% break %}
    {% endif %}
  {% endfor %}
  {% if the_next_site == null %}
    {% continue %}
  {% endif %}
  <li>
    <a href="{{ site.baseurl }}{{ the_next_site.name }}">{{ page_name }}</a> - {{ description }}
  </li>
{% endfor %}
</ul>

<h3 id="available-pages">Other pages</h3>
<ul>
{% for repo in site.github.public_repositories %}
  {% if repo.has_pages and repo.name != site.github.repository_name and !repo.fork %}
    {% assign page_name = repo.name %}
    {% assign description = repo.description %}
    {% if site.repohash[page_name] %}
      {% continue %}
    {% endif %}
  <li>
    <a href="{{ site.baseurl }}{{ repo.name }}">{{ page_name }}</a> - {{ description }}
  </li>
  {% endif %}
{% endfor %}
</ul>
