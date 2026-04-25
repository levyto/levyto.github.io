---
layout: default
title: Publications
---

## Publications

{% assign journal_pubs = site.data.publications | where: "type", "journal" | sort: "year" | reverse %}

{% assign conference_pubs = site.data.publications | where: "type", "conference" | sort: "sort_date" | reverse %}

{% assign thesis_pubs = site.data.publications | where: "type", "thesis" | sort: "year" | reverse %}

{% if journal_pubs.size > 0 %}
  <h3 class="pub-year" style="margin-bottom:15px; margin-top:15px;">Peer-reviewed Journal Articles</h3>

  {% assign pub_index = journal_pubs.size %}
  <ul class="publication-list">
    {% for pub in journal_pubs %}
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

            <em>{{ pub.venue }}</em>{% if pub.volume and pub.volume != "" %}, {{ pub.volume }}{% endif %}{% if pub.number and pub.number != "" %}({{ pub.number }}){% endif %}{% if pub.pages and pub.pages != "" %}, {{ pub.pages }}{% endif %}{% if pub.year %}, {{ pub.year }}{% endif %}
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
{% endif %}


{% if conference_pubs.size > 0 %}
  <h3 class="pub-year" style="margin-bottom:15px; margin-top:25px;">Conference Contributions</h3>

  {% assign pub_index = conference_pubs.size %}
  <ul class="publication-list">
    {% for pub in conference_pubs %}
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
            <strong>{{ pub.title }}</strong>{% if pub.label and pub.label != "" %} <span class="pub-label">({{ pub.label }})</span>{% endif %}<br>

            <em>{{ pub.venue }}</em>{% if pub.pages and pub.pages != "" %}, {{ pub.pages }}{% endif %}
            <br>

            {% if pub.note and pub.note != "" %}
              {{ pub.note }}
            {% endif %}
            {% if pub.year %}
              {{ pub.year }}<br>            
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
{% endif %}


{% if thesis_pubs.size > 0 %}
  <h3 class="pub-year" style="margin-bottom:15px; margin-top:25px;">Theses</h3>

  {% assign pub_index = thesis_pubs.size %}
  <ul class="publication-list">
    {% for pub in thesis_pubs %}
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
            <strong>{{ pub.title }}</strong>{% if pub.label and pub.label != "" %} <span class="pub-label">({{ pub.label }})</span>{% endif %}<br>

            <em>{{ pub.venue }}</em>{% if pub.year %}, {{ pub.year }}{% endif %}
            <br>

            {% if pub.note and pub.note != "" %}
              {{ pub.note }}<br>
            {% endif %}

            {% assign sep = false %}

            {% if pub.pdf and pub.pdf != "" %}
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
{% endif %}