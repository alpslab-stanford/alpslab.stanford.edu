---
 layout: default
 title: News
 permalink: news.html
---

<ul>
{% for post in site.posts %}
  <article>
    <h2>
        {{ post.title }}
    </h2>
    <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
    {{ post.content }}
  </article>
{% endfor %}
</ul>