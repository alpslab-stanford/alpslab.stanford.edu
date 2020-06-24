---
 layout: default
 title: Blog
 permalink: blog.html
---

<ul>
{% for post in site.posts %}
  <article>
    <h2>
        {{ post.title }}
   </h2>
    <big><i> {{ post.author}} </i>
    </big> <br>
    <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
    <br><br>
    {{ post.content }}
  </article>
{% endfor %}
</ul>

<!-- <a class="twitter-timeline" href="https://twitter.com/ALPSLabStanford?ref_src=twsrc%5Etfw">Tweets by ALPSLabStanford</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> -->

<!--<a class="twitter-timeline" data-width="600" data-theme="light" data-link-color="#2B7BB9" href="https://twitter.com/ALPSLabStanford?ref_src=twsrc%5Etfw">Tweets by ALPSLabStanford</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>-->