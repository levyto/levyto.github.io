---
layout: default
title: Publications
---

## Publications

{% assign pubs_sorted = site.data.publications | sort: "year" %}
{% assign pubs_by_year = pubs_sorted | reverse | group_by: "year" %}
{% assign pub_index = site.data.publications.size %}

{% for year_group in pubs_by_year %}
  <h3 class="pub-year" style="margin-bottom:15px">{{ year_group.name }}</h3>

  <ul class="publication-list">
    {% for pub in year_group.items %}
      <li class="publication-item" id="{{ pub.key }}">
        <div class="pub-row">
          <div class="pub-number">
            {{ pub_index }}.
          </div>
          <div class="pub-body">
            {% for author in pub.authors %}
              {{ author }}{% unless forloop.last %}, {% endunless %}
            {% endfor %}
            
            <br>
            <strong>{{ pub.title }}</strong><br>

            {% if pub.type == "journal" %}
              <em>{{ pub.venue }}</em>{% if pub.volume and pub.volume != "" %}, {{ pub.volume }}{% endif %}{% if pub.number and pub.number != "" %}({{ pub.number }}){% endif %}{% if pub.pages and pub.pages != "" %}, {{ pub.pages }}{% endif %}{% if pub.year %}, {{ pub.year }}{% endif %}
            {% elsif pub.type == "conference" %}
              <em>{{ pub.venue }}</em>{% if pub.pages and pub.pages != "" %}, {{ pub.pages }}{% endif %}{% if pub.year %}, {{ pub.year }}{% endif %}
            {% elsif pub.type == "thesis" %}
              <em>{{ pub.venue }}</em>{% if pub.year %}, {{ pub.year }}{% endif %}
            {% else %}
              <em>{{ pub.venue }}</em>{% if pub.year %}, {{ pub.year }}{% endif %}
            {% endif %}
            <br>

            {% if pub.note and pub.note != "" %}
              {{ pub.note }}<br>
            {% endif %}

            {% assign sep = false %}

            {% if pub.doi and pub.doi != "" %}
              <a href="https://doi.org/{{ pub.doi }}">DOI</a>
              {% assign sep = true %}
            {% endif %}

            {% if pub.pdf and pub.pdf != "" %}
              {% if sep %} | {% endif %}
              <a href="{{ pub.pdf | relative_url }}">PDF</a>
              {% assign sep = true %}
            {% endif %}

            {% if pub.slides and pub.slides != "" %}
              {% if sep %} | {% endif %}
              <a href="{{ pub.slides | relative_url }}">Slides</a>
              {% assign sep = true %}
            {% endif %}

            {% if pub.bib and pub.bib != "" %}
              {% if sep %} | {% endif %}
              <a href="{{ pub.bib | relative_url }}">BibTeX</a>
              {% assign sep = true %}
            {% endif %}

            {% if pub.url and pub.url != "" %}
              {% if sep %} | {% endif %}
              <a href="{{ pub.url }}">URL</a>
              {% assign sep = true %}
            {% endif %}        
          </div>
        </div>
      </li>

      {% assign pub_index = pub_index | minus: 1 %}
    {% endfor %}
  </ul>
{% endfor %}