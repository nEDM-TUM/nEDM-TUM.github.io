---
title: nEDM Experiment Documentation 
layout: basic
---

## nEDM Experiment documentation

This page provides documentation for software and systems used in the neutron
electric dipole moment (nEDM) experiment located at the Technische Universität
München (FRM-II).


<h3 id="available-pages1">Available pages1</h3>
<ul>
{% for repo in site.github.public_repositories %}
{% if repo.has_pages %}
{% assign page_name = repo.name %}
{% assign description = repo.description %}
{% if site.repohash[page_name] %}
  {% assign p = site.repohash[page_name] %}
  {% assign page_name = p.name %}
  {% if p.description %}
    {% assign description = p.description %}
  {% endif %}
{% endif %}
  <li>
    <a href="{{ site.baseurl }}{{ repo.name }}">{{ page_name }}</a> - {{ description }}
  </li>
{% endif %}
{% endfor %}
</ul>

### Available pages
* [System Overview](System-Overview) - Set of pages describing the
general functionality of many of the (non-software) systems used in the nEDM
experiment.
* [nEDM Interface](nEDM-Interface) - Page describing the web interface used for
control of devices and visualization of data in the experiment.
* [pynedm](Python-Slow-Control) - Provides a set of python tools for controlling devices and communicating with the central CouchDB server used in the experiment.

