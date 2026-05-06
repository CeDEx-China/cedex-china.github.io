---
title: People
permalink: /people/
nav: true
nav_order: 2
---

CeDEx China brings together researchers, faculty members, and lab management with expertise in behavioural and experimental economics.

<ul class="nav nav-tabs mt-4" id="peopleTabs" role="tablist">
  {% for section in site.data.people %}
  {% assign tab_id = section.group | slugify %}
  <li class="nav-item">
    <a class="nav-link {% if forloop.first %}active{% endif %}"
       id="{{ tab_id }}-tab"
       data-toggle="tab"
       href="#{{ tab_id }}"
       role="tab"
       aria-controls="{{ tab_id }}"
       aria-selected="{% if forloop.first %}true{% else %}false{% endif %}">
      {{ section.group }}
    </a>
  </li>
  {% endfor %}
</ul>

<div class="tab-content mt-4" id="peopleTabContent">
  {% for section in site.data.people %}
  {% assign tab_id = section.group | slugify %}
  <div class="tab-pane fade {% if forloop.first %}show active{% endif %}"
       id="{{ tab_id }}"
       role="tabpanel"
       aria-labelledby="{{ tab_id }}-tab">
    <div class="row">
      {% for person in section.members %}
      <div class="col-12 col-sm-6 col-lg-4 mb-3 d-flex">
        <div class="card w-100" style="border-radius:8px; border-color: var(--global-divider-color);">
          <div class="card-body" style="padding: 1rem 1.1rem;">
            <h6 class="card-title mb-1" style="font-weight:600; font-size:0.9rem;">
              {{ person.name }}{% if person.email %}&nbsp;<a href="mailto:{{ person.email }}" title="{{ person.email }}" style="font-size:0.85em;">✉️</a>{% endif %}
            </h6>
            <p class="mb-1" style="font-size:0.78rem; color: var(--global-theme-color); font-weight:500;">{{ person.role }}</p>
            <p class="mb-1" style="font-size:0.78rem; color: var(--global-text-color-light);">{{ person.affiliation }}</p>
            {% if person.focus %}
            <p class="mb-0" style="font-size:0.78rem; color: var(--global-text-color);">{{ person.focus }}</p>
            {% endif %}
          </div>
        </div>
      </div>
      {% endfor %}
    </div>
  </div>
  {% endfor %}
</div>