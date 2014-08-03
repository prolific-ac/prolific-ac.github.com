---
layout: page
---
<!--title: Hello World!
tagline: Supporting tagline
-->
{% for post in site.posts %}
  {% unless post.draft %}
  <li>
    <span>{{ post.date | date: "%B %e, %Y" }}</span> <a href="{{ post.url }}">{{ post.title }}</a>
     {{ post.excerpt }}
  </li>

  {% endunless %}
{% endfor %}