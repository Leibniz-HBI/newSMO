---
title: Publications
layout: archive
permalink: /tags/publication/
classes: wide
author_profile: false
---

<style>
.publication-intro {
  max-width: 58rem;
  margin-bottom: 2.25rem;
}

.publication-section {
  margin-top: 2.75rem;
}

.publication-section > h2 {
  margin-bottom: 0.35rem;
}

.publication-section-description {
  margin-top: 0;
  margin-bottom: 1.25rem;
}

.publication-list {
  margin: 0;
  padding: 0;
  list-style: none;
}

.publication-item {
  margin: 0;
  padding: 1.15rem 0 1.25rem;
  border-bottom: 1px solid rgba(127, 127, 127, 0.28);
}

.publication-item:first-child {
  border-top: 1px solid rgba(127, 127, 127, 0.28);
}

.publication-title {
  margin: 0 0 0.35rem;
  font-size: 1.05em;
  line-height: 1.4;
}

.publication-citation {
  margin: 0;
  line-height: 1.5;
}

.publication-year {
  font-weight: 700;
}

.publication-links {
  margin-top: 0.45rem;
  font-size: 0.88em;
}

.publication-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.3rem 0.4rem;
  margin-top: 0.55rem;
}

.publication-tag {
  display: inline-block;
  padding: 0.12rem 0.42rem;
  border: 1px solid rgba(127, 127, 127, 0.35);
  border-radius: 0.3rem;
  font-size: 0.74em;
  line-height: 1.45;
  text-decoration: none;
  white-space: nowrap;
}

.publication-tag:hover {
  text-decoration: underline;
}
</style>

<p class="publication-intro">
  Publications are divided into two groups: outputs directly associated with the
  <strong>Social Media Observatory (SMO)</strong> and
  <strong>SMO-relevant publications from team members</strong>.
</p>

{% assign publications = site.tags.publication | sort: "publication_sort_date" | reverse %}

<section class="publication-section">
  <h2>SMO publications</h2>
  <p class="publication-section-description">
    Publications and research outputs directly associated with the Social Media Observatory.
  </p>

  <ol class="publication-list">
  {% for post in publications %}
    {% if post.publication_category == "smo" %}
    <li class="publication-item">
      <h3 class="publication-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      <p class="publication-citation">
        <span class="publication-year">{{ post.publication_year }}</span>
        &nbsp;·&nbsp; {{ post.citation }}
      </p>
      {% if post.publication_url %}
      <div class="publication-links">
        <a href="{{ post.publication_url }}">Publication / full text</a>
      </div>
      {% endif %}
      <div class="publication-tags" aria-label="Publication tags">
      {% for tag in post.tags %}
        {% unless tag == "publication" %}
          {% assign tag_slug = tag | slugify %}
          <a class="publication-tag" href="{{ '/tags/' | append: tag_slug | append: '/' | relative_url }}">{{ tag }}</a>
        {% endunless %}
      {% endfor %}
      </div>
    </li>
    {% endif %}
  {% endfor %}
  </ol>
</section>

<section class="publication-section">
  <h2>SMO-relevant publications from team members</h2>
  <p class="publication-section-description">
    Publications by current or former SMO team members that are closely related to the
    observatory's substantive or methodological scope but are not classified as direct SMO outputs.
  </p>

  <ol class="publication-list">
  {% for post in publications %}
    {% if post.publication_category == "team" %}
    <li class="publication-item">
      <h3 class="publication-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      <p class="publication-citation">
        <span class="publication-year">{{ post.publication_year }}</span>
        &nbsp;·&nbsp; {{ post.citation }}
      </p>
      {% if post.publication_url %}
      <div class="publication-links">
        <a href="{{ post.publication_url }}">Publication / full text</a>
      </div>
      {% endif %}
      <div class="publication-tags" aria-label="Publication tags">
      {% for tag in post.tags %}
        {% unless tag == "publication" %}
          {% assign tag_slug = tag | slugify %}
          <a class="publication-tag" href="{{ '/tags/' | append: tag_slug | append: '/' | relative_url }}">{{ tag }}</a>
        {% endunless %}
      {% endfor %}
      </div>
    </li>
    {% endif %}
  {% endfor %}
  </ol>
</section>
