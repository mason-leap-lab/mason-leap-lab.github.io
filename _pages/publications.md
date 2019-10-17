---
title: "LeapLab - Publications"
layout: gridlay
excerpt: "LeapLab -- Publications."
sitemap: false
permalink: /publications/
---


# Publications

## Highlights

(For a full list see [below](#conferences-and-workshops) or go to 
<a target="_blank" href="https://scholar.google.com/citations?user=TMGwBH0AAAAJ&hl=en">Google Scholar</a>.)

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="well">
  <pubtit>{{ publi.title }}</pubtit>
  <p><strong><a target="_blank" href="{{ publi.conf.url }}">{{ publi.conf.display }}</a></strong>  &nbsp;<a target="_blank" class="btn btn-primary btn-xs" role="button" href="{{ site.url }}/{{ publi.link.url }}"> {{ publi.link.display }}</a></p>
  <img src="{{ site.url }}{{ site.baseurl }}/images/research/{{ publi.image }}" class="img-responsive" width="33%" style="float: left" />
  <p>{{ publi.description }}</p>
  <p><em>{{ publi.authors }}</em></p>
  <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
  <p> {{ publi.news2 }}</p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<!--p> &nbsp; </p-->


## Conferences and Workshops

{% for publi in site.data.publist %}

  <strong>{{ publi.title }}</strong> <br />
  <em>{{ publi.authors }} </em><br /><a target="_blank" href="{{ publi.conf.url }}"> {{ publi.conf.display }}</a>&nbsp;&nbsp; 
  <a target="_blank" class="btn btn-primary btn-sm" role="button" href="{{ site.baseurl }}/{{ publi.link.url }}"> {{ publi.link.display }}</a>{% if publi.has_arxiv == 1 %}
  &nbsp;&nbsp;<a target="_blank" class="btn btn-success btn-sm" role="button" href="{{ publi.arxiv.url }}"> {{ publi.arxiv.display }}</a>{% endif %}{% if publi.has_src == 1 %}
  &nbsp;&nbsp;<a target="_blank" class="btn btn-warning btn-sm" href="{{ publi.src.url }}"> {{ publi.src.display }}</a>
  {% endif %}
  

{% endfor %}


## Journals

{% for publi in site.data.journallist %}

  <strong>{{ publi.title }}</strong> <br />
  <em>{{ publi.authors }} </em><br /><a target="_blank" href="{{ publi.conf.url }}"> {{ publi.conf.display }}</a>&nbsp;&nbsp; {% if publi.has_pdf == 1 %}
  <a target="_blank" class="btn btn-primary btn-sm" role="button" href="{{ site.baseurl }}/{{ publi.link.url }}"> {{ publi.link.display }}</a>
  {% endif %}
  

{% endfor %}


## Book Chapters

{% for publi in site.data.booklist %}

  <strong>{{ publi.title }}</strong> <br />
  <em>{{ publi.authors }} </em><br /><a target="_blank" href="{{ publi.conf.url }}"> {{ publi.conf.display }}</a>&nbsp;&nbsp;  {% if publi.has_pdf == 1 %}
  <a target="_blank" class="btn btn-primary btn-sm" role="button" href="{{ site.baseurl }}/{{ publi.link.url }}"> {{ publi.link.display }}</a>
  {% endif %}
  

{% endfor %}


## Posters and Demos

{% for publi in site.data.posterlist %}

  <strong>{{ publi.title }}</strong> <br />
  <em>{{ publi.authors }} </em><br /><a target="_blank" href="{{ publi.conf.url }}"> {{ publi.conf.display }}</a>&nbsp;&nbsp; {% if publi.has_pdf == 1 %}
  <a target="_blank" class="btn btn-primary btn-sm" role="button" href="{{ site.baseurl }}/{{ publi.link.url }}"> {{ publi.link.display }}</a>
  {% endif %}
  

{% endfor %}
