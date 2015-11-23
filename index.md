---
layout: page
title: Sahil Seth
excerpt: "genomics enthusiast living in Houston"
modified: 2014-08-08T19:44:38.564948-04:00
---


I am a Associate Scientist at [Institute of Applied Cancer Science](http://www.mdanderson.org/education-and-research/departments-programs-and-labs/programs-centers-institutes/institute-for-applied-cancer-science/index.html)/[Genomic Medine](http://www.mdanderson.org/education-and-research/departments-programs-and-labs/departments-and-divisions/genomic-medicine/index.html), [MD Anderson Cancer Center](http://www.cancermoonshots.org/research/).

During the last few years I have collaborated on several different problems in cancer genomics; you may find list of my [publications on scholar](https://scholar.google.com/citations?user=aXwxLwEAAAAJ). I have also created several software packages, which are available on [github](http://github.com/sahilseth).

<ul class="post-list">
{% for post in site.posts limit:5 %}
  <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>{% if post.excerpt %} <span class="excerpt">{{ post.excerpt }}</span>{% endif %}</a></article></li>
{% endfor %}
</ul>

<p></p>
<a class="twitter-timeline" href="https://twitter.com/sethsa" data-widget-id="668688191826694144">Tweets by @sethsa</a>
<script>
!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';
if(!d.getElementById(id)){
  js=d.createElement(s);
  js.id=id;js.src=p+"://platform.twitter.com/widgets.js";
  fjs.parentNode.insertBefore(js,fjs);
  }}(document,"script","twitter-wjs");
</script>
