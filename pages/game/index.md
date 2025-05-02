---
layout: default
title: Game
permalink: /game/
pagination:
  enabled: true
  category: game
---

<div class="flex-center" id="content-wrapper" style="transform: none;"><div class="container row-x1" style="transform: none;">
<!-- Post -->        
<main class="has-cs2" id='main-wrapper'><div class="main section" id="main" name="Main Posts"><div class="widget Blog" data-version="2" id="Blog1">

  {% assign posts = paginator.posts %}
  {% assign category_name = "Game" %}
<div class="blog-posts-wrap">
  <div class="queryMessage "><span class="query-info query-label query-success">{{ category_name }}</span></div>

  <div>
    {% if posts and posts.size > 0 %}
    <div class="blog-posts hfeed index-post-wrap" id="post-list">
      {% for post in paginator.posts %}
      <article class="blog-post hentry index-post post-{{ forloop.index0 }}">
        <a class="entry-image-wrap {% if post.video %} is-video {% elsif post.image %} is-image {% endif %}" href="{{ post.url | relative_url }}" title="{{ post.title }}">
          {% if post.video %}
          <span class="entry-thumb lazy-ify" data-image="{{ post.video }}" style="background-image:url({{ post.video }})"></span>
          {% elsif post.image %}
          <span class="entry-thumb lazy-ify" data-image="{{ post.image }}" style="background-image:url({{ post.image }})"></span>
          {% else %}
          <span class="entry-thumb lazy-ify" data-image="default-image.jpg" style="background-image:url(default-image.jpg)"></span>
          {% endif %}
        </a>
        <div class="entry-header">
          <span class="entry-category">{{ post.categories[0] }}</span>
          <h2 class="entry-title"><a class="entry-title-link" href="{{ post.url | relative_url }}" rel="bookmark" title="{{ post.title }}">{{ post.title }}</a></h2>
          <p class="line-clamp-3">{{ post.excerpt | strip_html | truncatewords:15 }}</p>
          {% assign author = site.data.authors[post.author] %}
          {% if author.name %}
          <div class="entry-meta">
            <span class="entry-author">
              <span class="by">by</span>
              <span class="author-name"><a href="{{ '/author/' | append: post.author | relative_url }}">{{ author.name }}</a></span>
              <span class="entry-time">
                <span class="on">-</span>
                <time class="published" datetime="{{ post.date | date_to_string }}">{{ post.date | date_to_string }}</time>
              </span>
            </span>
          </div>
          {% endif %}
        </div>
      </article>
      {% endfor %}
    </div>
    {% else %}
      <p>No game posts available.</p>
    {% endif %}
  </div> </div>

  {% include pagination.html %}

</div></div></main>
<!-- End Post -->
<!-- Sidebar -->
<aside id="sidebar-wrapper">
   <div class="sidebar supermag-pro-widget-ready section" id="sidebar" name="Sidebar">
      {% include sidebar.html %}
   </div>
</aside>
<!--End Sidebar -->
</div></div>
