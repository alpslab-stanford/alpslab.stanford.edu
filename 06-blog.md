---
 layout: default
 title: Blog
 permalink: blog.html
---

<ul class='post-list'>
{% for post in site.posts %}
<div class='post_element'>
  <article>
    <h2>
        {{ post.title }}
   </h2>
    <big><i> {{ post.author}} </i>
    </big> <br>
    <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
    <br><br>
    <div class='content_preview'>
      {{ post.content }}
    </div>
  </article>
    <p><a href="{{ post.permalink }}">See More</a></p>
    </div>

{% endfor %}
</ul>

<!-- <a class="twitter-timeline" href="https://twitter.com/ALPSLabStanford?ref_src=twsrc%5Etfw">Tweets by ALPSLabStanford</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> -->

<!--<a class="twitter-timeline" data-width="600" data-theme="light" data-link-color="#2B7BB9" href="https://twitter.com/ALPSLabStanford?ref_src=twsrc%5Etfw">Tweets by ALPSLabStanford</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>-->