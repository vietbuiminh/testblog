---
title: coding
layout: main
description: A few of my featured projects.
categories: [coding]
---
Most of my coding projects are on github.

A few of my featured projects.
{% assign j = 0 %}
{% assign sorted = site.categories.coding | sort: 'date' | reverse  %}
{% for post in sorted %}

<div style="animation-delay:calc({% increment j %} * 0.2s);" class="gallery">
    <a target="_blank" href="{{ post.image }}">
        <img class="lazy" data-src="{{ post.image }}" alt="{{ post.img-alt }}" />
    </a>
    <div class="desc">
        <h2 style="margin-top: 0; line-height: 1em;">{{ post.full-title | upcase }}</h2>
        <p>{{ post.description }}</p>
        <span class="bottomrow">
            <span class="tags">
                <a class="button link" href="{{ post.url }}">
                    read more &#x2192;</a>
            </span>
            <span class="tags">
                {% for tag in post.tags %}
                <a class="tag link" href="{{ "tags/" | append: tag | relative_url }}">#{{ tag }}</a>
                {% endfor %}
            </span>
        </span>
    </div>
</div>

{% endfor %}
