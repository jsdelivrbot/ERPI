---
title: "ERPI"
layout: single
permalink: /fr/
locale: fr-FR
lang: fr


sidebar:
  nav: ""

excerpt: "Equipe de Recherche sur les Processus Innovatifs"
header:
  overlay_image: /assets/images/home/banner-ERPI.jpg
  overlay_filter: 0.1
  show_overlay_excerpt: true 
  image_description: "Equipe de Recherche sur les Processus Innovatifs"
  cta_label: "Lire plus"
  cta_url: "http://erpi.univ-lorraine.fr/fr/about"

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


**L’ERPI (Équipe de Recherche sur les Processus Innovatifs)** est un des laboratoires de [l'Université de Lorraine](http://univ-lorraine.fr), labellisé Équipe d’Accueil (EA n° 3767) par le Ministère de l’Enseignement Supérieur et de la Recherche. 
L'ERPI est membre de la **FR 2863 : Fédération de Recherche Jacques Villermaux pour la Mécanique, l'Energie, les Procédés (FR JV)** et est rattaché au pole scientifique EMPP - Énergie, Mécanique, Procédés, Produits. 
Par ailleurs, les relations qu’entretient [l’ENSGSI](http://ensgsi.univ-lorraine.fr) (Ecole de l'Innovation) avec ce laboratoire sont historiques.

L’équipe ERPI a pour vocation de mener des recherches dans le domaine de la conduite et du pilotage des processus innovatifs. 
L’ERPI est un laboratoire de **Génie Industriel** spécialisé dans l’étude des processus d’innovation. Ses activités concernent les méthodes, les outils et les compétences permettant l’optimisation du pilotage des projets innovants.

Le projet scientifique de l’ERPI porte sur **les étapes amont du processus d’innovation technologique** c’est-à-dire les phases allant de l’émergence des idées jusqu’aux phases préalables à la matérialisation (plans numériques ou formulation). La spécificité des approches de l'ERPI par rapport au paysage international de la recherche en innovation est de considérer le produit comme un système intégrant : les caractéristiques du produit lui-même ainsi que les éléments descriptifs de l’activité industrielle correspondante (fabrication, maintenance, distribution…).

## Partenaires

{% include gallery %}



## Actualités

{% assign posts = site.posts | where: "lang", "fr"  %}
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

<a href="{{ site.url }}/fr/news/" class="btn btn--primary">Lire tous les actualités</a>{: .notice--info}











