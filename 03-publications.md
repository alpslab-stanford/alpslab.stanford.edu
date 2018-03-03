---
layout: default
title: Publications
permalink: publications.html
---
## Pending

{% bibliography --template bibtemplate --style _bibliography/alpslab.csl --query @*[year=Manuscript] %}

### To appear

{% bibliography --template bibtemplate --style _bibliography/alpslab.csl --query @*[year=to appear] %}

{% for year in (2006..{{site.max_year}}) reversed %}

### Submitted

{% bibliography --template bibtemplate --style _bibliography/alpslab.csl --query @*[year=submitted] %}

{% for year in (2006..{{site.max_year}}) reversed %}

<a class="subtle_link" name="{{year}}"></a>
## {{year}}

{% bibliography --template bibtemplate --style _bibliography/alpslab.csl --query @*[year={{year}}] %}

{% endfor %}
