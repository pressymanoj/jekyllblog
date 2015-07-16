---
layout: page
title: Java
permalink: /java/
---

<div class="home">

  <h1 class="page-heading">Posts</h1>

  <ul class="post-list">
    {% for post in site.posts %}
    {{ request.myvar }}
      <li>
      <div class="row container">
    	
        <div class="col-lg-6 col-md-6 col-xs-12">

        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
        <p>{{ post.content | strip_html | truncatewords: 50 }}</p>
        <a href="{{ post.url | prepend: site.baseurl }}">Read More</a>
        </div>
        <div class="col-lg-6 col-md-6 col-xs-12 col_date">
        <p class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</p>
        </div>
        </div>
      </li>
    {% endfor %}
  </ul>

  <!--<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>-->

</div>
