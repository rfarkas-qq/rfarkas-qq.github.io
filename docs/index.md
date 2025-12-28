---
layout: default
title: Home
---

## Obsah

## preložené sumarizácie videí z kanála DOAC 

YouTube: [DOAC](https://www.youtube.com/channel/UCGq-a57w-aPwyi3pW7XLiHw)

<ul>
  {% for page in site.pages %}
    {% if page.path contains "doac/" %}
      <li>
        <a href="{{ page.url | relative_url }}">{{ page.title | default: page.name }}</a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
