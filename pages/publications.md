---
layout: default
title: Publications
---

## Publications

{% assign pubs_by_year = site.data.publications | sort: "year" | reverse | group_by: "year" %}

{% for year_group in pubs_by_year %}
  <h3 class="pub-year" style="margin-bottom:15px">{{ year_group.name }}</h3>

  <ul class="publication-list">
    {% for pub in year_group.items %}
      <li class="publication-item">
        <strong>{{ pub.title }}</strong><br>

        {% for author in pub.authors %}
          {{ author }}{% unless forloop.last %}, {% endunless %}
        {% endfor %}
        <br>

        {% if pub.type == "journal" %}
          <em>{{ pub.venue }}</em>
          {% if pub.volume and pub.volume != "" %}
            , {{ pub.volume }}
          {% endif %}
          {% if pub.number and pub.number != "" %}
            ({{ pub.number }})
          {% endif %}
          {% if pub.pages and pub.pages != "" %}
            , {{ pub.pages }}
          {% endif %}
          {% if pub.year %}
            , {{ pub.year }}
          {% endif %}
        {% elsif pub.type == "conference" %}
          <em>{{ pub.venue }}</em>
          {% if pub.pages and pub.pages != "" %}
            , {{ pub.pages }}
          {% endif %}
          {% if pub.year %}
            , {{ pub.year }}
          {% endif %}
        {% elsif pub.type == "thesis" %}
          <em>{{ pub.venue }}</em>
          {% if pub.year %}
            , {{ pub.year }}
          {% endif %}
        {% else %}
          <em>{{ pub.venue }}</em>
          {% if pub.year %}
            , {{ pub.year }}
          {% endif %}
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

        {% if pub.url and pub.url != "" %}
          {% if sep %} | {% endif %}
          <a href="{{ pub.url }}">Link</a>
          {% assign sep = true %}
        {% endif %}

        {% if pub.pdf and pub.pdf != "" %}
          {% if sep %} | {% endif %}
          <a href="{{ pub.pdf | relative_url }}">PDF</a>
        {% endif %}
      </li>

    {% endfor %}
  </ul>
{% endfor %}