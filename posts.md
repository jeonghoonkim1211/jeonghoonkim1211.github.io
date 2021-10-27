# Centrarium [![Circle CI](https://circleci.com/gh/bencentra/centrarium/tree/master.svg?style=svg)](https://circleci.com/gh/bencentra/centrarium/tree/master)

A simple yet classy theme for your Jekyll website or blog. Customizable to fit your style or brand.

Built with these awesome libraries:
* [Bourbon][bourbon]
* [Neat][neat]
* [Bitters][bitters]
* [Refills][refills]
* [Font Awesome][fontawesome]
* [HighlightJS][highlightjs]
* [Lightbox][lightbox]

Here's a [demo](http://bencentra.com/centrarium). It also works on [GitHub Pages](http://bencentra.github.io/centrarium/). I also use it for [my own website][bencentra].

Inspired by dirkfabisch's [Mediator](https://github.com/dirkfabisch/mediator) theme, which I previously used for my own blog, as well as [Type Theme](http://rohanchandra.github.io/type-theme/).

Cover image by Chris M. Morris ([flickr][cover])

---
layout: page
title: "Posts"
permalink: /posts/
main_nav: true
---
{% for category in site.categories %}
  {% capture cat %}{{ category | first }}{% endcapture %}
  <h2 id="{{cat}}">{{ cat | capitalize }}</h2>
  {% for desc in site.descriptions %}
    {% if desc.cat == cat %}
      <p class="desc"><em>{{ desc.desc }}</em></p>
    {% endif %}
  {% endfor %}
  <ul class="posts-list">
  {% for post in site.categories[cat] %}
    <li>
      <strong>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </strong>
      <span class="post-date">- {{ post.date | date_to_long_string }}</span>
    </li>
