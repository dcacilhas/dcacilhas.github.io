---
layout: page
title:  Archives
permalink: /archives/
sortorder: 2
---
<div id="archives">

{% assign sortedcats = site.categories | sort %}
<section class="categories">
  <ul>
    {% for category in sortedcats  %}
    <li>
    <a class="category" href="#{{category | first}}">{{ category | first }}</a>
  </li>
    {% endfor %}
  </ul>
</section>

<section class="posts">
  {% for category in sortedcats %}

  <h3 id="{{category | first}}">{{ category | first }} ({{ category[1] | size }})</h3>
  <ul>
    {% assign pages = category[1] %}
    {% for page in pages | sort: 'date' %}
      <li>
        {{ page.date | date_to_string }}
        <a href="{{ site.BASE_PATH }}{{page.url}}">{{page.title}}</a>
      </li>

    {% endfor %}
  </ul>

  {% endfor %}

</section>

</div>