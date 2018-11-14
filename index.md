---
title: "ERPI"
layout: single
permalink: /
sidebar:
  nav: ""
lang: en

excerpt: "Equipe de Recherche sur les Processus Innovatifs"
header:
  overlay_image: /assets/images/home/banner-ERPI.jpg
  overlay_filter: 0.1
  show_overlay_excerpt: true 
  image_description: "Equipe de Recherche sur les Processus Innovatifs"
  cta_label: "More Info"
  cta_url: "http://erpi.univ-lorraine.fr/about"

intro: 
  - excerpt: '**Equipe de Recherche sur les Processus Innovatifs**'

gallery:
  - url: http://lf2l.fr/
    image_path: /assets/images/partners/LF2L-Vertical.jpg
    alt: "Lorraine Fab Living Lab"
    title: "Lorraine Fab Living Lab"

  - url: https://rrien.univ-littoral.fr/
    image_path: /assets/images/partners/RNI.jpg
    alt: "placeholder image 2"
    title: "Research Network on Innovation"
  
  - url: http://www.iceel.eu/fr/accueil.html
    image_path: /assets/images/partners/ICEEL.jpg
    alt: "Institute Carnot ICEEL"
    title: "Institute Carnot ICEEL"

   
---


{% include feature_row id="intro" type="center" %}

The **ERPI (Research team on innovation process)** is one of the [University of Lorraine](http://univ-lorraine.fr) research labs. It is labeled as such by the French Ministry of Higher Education, Research and Innovation. ERPI is a founding member of the Jacques Villermaux Federation and linked to the EMPP scientifique pole. ERPI has an historical link with the [ENSGSI](http://ensgsi.univ-lorraine.fr) ( Engineering School on Innovation).

ERPI is a research team on Industrial Engineering specialized on the research of innovation processes management. Its activities concerns the methods, tools and knowledges allowing to optimise innovation projects management.

The scientific project of the ERPI deals with the Fuzzy Front End off innovation that is to say from idea generation to materialization (CAD, formulation ...). ERPI differs to other innovation research laboratories by considering the product as a "integrating system".   


## Partners

{% include gallery %}


## Latest News

{% assign posts = site.posts | where: "lang", "en"  %}
{% for post in posts offset: 0 limit: 3 %}


{% if post.header.teaser %}
  {% capture teaser %}{{ post.header.teaser }}{% endcapture %}
{% else %}
  {% assign teaser = site.teaser %}
{% endif %}

{% if post.id %}
  {% assign title = post.title | markdownify | remove: "<p>" | remove: "</p>" %}
{% else %}
  {% assign title = post.title %}
{% endif %}

<div class="{{ include.type | default: "list" }}__item">
  <article class="archive__item" itemscope itemtype="http://schema.org/CreativeWork">
    {% if include.type == "grid" and teaser %}
      <div class="archive__item-teaser">
        <img src=
          {% if teaser contains "://" %}
            "{{ teaser }}"
          {% else %}
            "{{ teaser | relative_url }}"
          {% endif %}
          alt="">
      </div>
    {% endif %}

    <h2 class="archive__item-title" itemprop="headline">
      {% if post.link %}
        <a href="{{ post.link }}">{{ title }}</a> <a href="{{ post.url | relative_url }}" rel="permalink"><i class="fas fa-link" aria-hidden="true" title="permalink"></i><span class="sr-only">Permalink</span></a>
      {% else %}
        <a href="{{ post.url | relative_url }}" rel="permalink">{{ title }}</a>
      {% endif %}
    </h2>

    {% if post.read_time %}
    <p class="page__meta">{{ post.date  | date: "%B %-d, %Y" }} &emsp;| &emsp; <i class="far fa-clock" aria-hidden="true"></i> {% include read-time.html %}</p>
    {% endif %}
    {% if post.excerpt %}<p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 400 }}</p>
    {% endif %}

    <p><a href="{{ post.url | relative_url }}" class="align-right btn btn--primary">{{ site.data.ui-text[page.lang].more_label | default: "Read more" }}</a></p> 

  </article>
</div>
{% endfor %}

--- 

<a href="{{ site.url }}/news/" class="btn btn--primary">Lire tous les actualités</a>{: .notice--info}



<p><a href="{{ site.url }}/news/" class="btn btn--primary">{{ site.data.ui-text[page.lang].more_label | default: "Read more" }}</a></p> 


