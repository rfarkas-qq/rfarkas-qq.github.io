---
layout: default
title: Home
---

## Obsah

## preložené sumarizácie videí z kanála DOAC 

YouTube: [DOAC](https://www.youtube.com/channel/UCGq-a57w-aPwyi3pW7XLiHw)

{% assign sections = "" | split: "" %}

{%- for page in site.pages -%}
  {%- assign parts = page.path | split: '/' -%}
  {%- if parts.size > 1 -%}
    {%- assign topdir = parts[0] -%}
    {%- if topdir topdir != "_site" -%}
      {%- unless sections contains topdir -%}
        {%- assign sections = sections | push: topdir -%}
      {%- endunless -%}
    {%- endif -%}
  {%- endif -%}
{%- endfor -%}

{%- for section in sections -%}
  <h2>{{ section | replace: '-', ' ' | capitalize }}</h2>
  <ul>
    {%- for page in site.pages -%}
      {%- assign parts = page.path | split: '/' -%}
      {%- if parts[0] == section -%}
        <li>
          <a href="{{ page.url | relative_url }}">
            {{ page.title | default: page.name }}
          </a>
        </li>
      {%- endif -%}
    {%- endfor -%}
  </ul>
{%- endfor -%}
