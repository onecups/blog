---
layout: default
title: Game
pagination:
  enabled: true
---

<div class="flex-center" id="content-wrapper" style="transform: none;">
  <div class="container row-x1" style="transform: none;">
    <div class="content-section section" id="content-section-2" name="Content Section 2">
      <div class="widget HTML is-visible type-grid" data-version="2" id="HTML7">
        <div class="widget-title title-wrap">
          <h3 class="title">Game Online Unblocked</h3>
        </div>

        {% assign posts = paginator.posts | where_exp: "post", "post.categories contains 'game'" %}

        {% if posts.size > 0 %}
        <div class="widget-content">
          <div class="content-block grid-items">
            {% for post in posts %}
            <div class="grid-item item-{{ forloop.index0 }}">
              <a title="{{ post.title }}" class="entry-image-wrap {% if post.video %} is-video {% elsif post.image %} is-image {% endif %}" href="{{ post.url | relative_url }}">
                {% if post.video %}
                <span class="entry-thumb lazy-ify" data-image="{{ post.video }}" style="background-image:url({{ post.video }})"></span>
                {% elsif post.image %}
                <span class="entry-thumb lazy-ify" data-image="{{ post.image }}" style="background-image:url({{ post.image }})"></span>
                {% else %}
                <span class="entry-thumb lazy-ify" data-image="default-image.jpg" style="background-image:url(default-image.jpg)"></span>
                {% endif %}
              </a>
              <div class="entry-header">
                <h2 class="entry-title">
                  <a title="{{ post.title }}" href="{{ post.url | relative_url }}">{{ post.title }}</a>
                </h2>
                <div class="entry-meta">
                  <span class="entry-time mi">
                    <time class="published" datetime="{{ post.date | date: '%Y-%m-%d' }}">
                      {{ post.date | date: '%Y-%m-%d' }}
                    </time>
                  </span>
                </div>
              </div>
            </div>
            {% endfor %}
          </div>
        </div>

        <!-- Include pagination -->
        {% include pagination.html %}
        {% else %}
        <p>No game posts available.</p>
        {% endif %}
      </div>
    </div>
  </div>
</div>
