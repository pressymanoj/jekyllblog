---
layout: page
title: Java
permalink: /java/
---

<div class="home">
	{{ request.myvar }}


  <ul class="post-list">
    {% for post in site.posts %}
    {% if post.tags contains 'java' %}
      <li>
	  <div class="container">
      <div class="row ">
    	
        <div class="col-lg-8 col-md-8 col-xs-12">

        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
        <p>{{ post.content | strip_html | truncatewords: 50 }}</p>
        
        </div>
        <div class="col-lg-4 col-md-4 col-xs-12 col_date">
        <p class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</p>
        </div>
        </div>
		<a class="read_more" href="{{ post.url | prepend: site.baseurl }}">Read More</a>
		</div>
      </li>
	  {% endif %}
    {% endfor %}
  </ul>

  <!--<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>-->

</div>