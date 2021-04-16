---
layout: default
title: Publications
permalink: publications.html
---
## Pending

### To appear

{% bibliography --template bibtemplate --style _bibliography/alpslab.csl --query @*[year=to appear] %}

<!--### Submitted

{% bibliography --template bibtemplate --style _bibliography/alpslab.csl --query @*[year=submitted] %}

{% for year in (2011..2021) reversed %}
-->
<a class="subtle_link" name="{{year}}"></a>
## {{year}}

{% bibliography --template bibtemplate --style _bibliography/alpslab.csl --query @*[year={{year}}] %}

{% endfor %}
