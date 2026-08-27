---
title: Publications
layout: single
permalink: /tags/publication/
---

The publications listed here are divided into two groups: outputs directly associated with the **Social Media Observatory (SMO)** and **SMO-relevant publications from team members**.

{% assign publications = site.tags.publication | sort: "publication_sort_date" | reverse %}
{% assign smo_publications = publications | where: "publication_category", "smo" %}
{% assign team_publications = publications | where: "publication_category", "team" %}

## SMO publications

{% for post in smo_publications %}
### [{{ post.title }}]({{ post.url | relative_url }})

**{{ post.publication_year }}** · {{ post.citation }}

{% assign topical_tags = post.tags | where_exp: "tag", "tag != 'publication'" %}
{% if topical_tags.size > 0 %}
<small>Tags:
{% for tag in topical_tags %}
  {% assign tag_slug = tag | slugify %}
  <a href="{{ '/tags/#' | append: tag_slug | relative_url }}">{{ tag }}</a>{% unless forloop.last %} · {% endunless %}
{% endfor %}
</small>
{% endif %}

{% endfor %}

## SMO-relevant publications from team members

These publications were produced by current or former SMO team members and are closely related to the observatory's substantive or methodological scope, but are not classified here as direct SMO outputs.

{% for post in team_publications %}
### [{{ post.title }}]({{ post.url | relative_url }})

**{{ post.publication_year }}** · {{ post.citation }}

{% assign topical_tags = post.tags | where_exp: "tag", "tag != 'publication'" %}
{% if topical_tags.size > 0 %}
<small>Tags:
{% for tag in topical_tags %}
  {% assign tag_slug = tag | slugify %}
  <a href="{{ '/tags/#' | append: tag_slug | relative_url }}">{{ tag }}</a>{% unless forloop.last %} · {% endunless %}
{% endfor %}
</small>
{% endif %}

{% endfor %}
