---
layout: default
title: Publications
permalink: publications.html
---
## Pending

### To appear

{% bibliography --template bibtemplate --style _bibliography/alpslab-apa5.csl --query @*[year=to appear] %}

### Submitted

{% bibliography --template bibtemplate --style _bibliography/alpslab-apa5.csl --query @*[year=submitted] %}

{% for year in (2011..2040) reversed %}

<a class="subtle_link" name="{{year}}"></a>
## {{year}}

{% bibliography --template bibtemplate --style _bibliography/alpslab-apa5.csl --query @*[year={{year}}] %}

{% endfor %}
