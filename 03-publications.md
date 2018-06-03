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

{% for year in (2011..{{site.max_year}}) reversed %}

<a class="subtle_link" name="{{year}}"></a>
## {{year}}

{% bibliography --template bibtemplate --style _bibliography/alpslab-apa5.csl --query @*[year={{year}}] %}

{% endfor %}
