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

<div class="tab-content mt-3" id="peopleTabContent">
  {% for section in site.data.people %}
  {% assign tab_id = section.group | slugify %}
  <div class="tab-pane fade {% if forloop.first %}show active{% endif %}"
       id="{{ tab_id }}"
       role="tabpanel"
       aria-labelledby="{{ tab_id }}-tab">
    <div class="table-responsive">
      <table class="table table-sm table-striped">
        <thead>
          <tr>
            <th>Name</th>
            <th>Role</th>
            <th>Affiliation</th>
            <th>Research Focus</th>
          </tr>
        </thead>
        <tbody>
          {% for person in section.members %}
          <tr>
            <td>{{ person.name }}{% if person.email %} <a href="mailto:{{ person.email }}" title="{{ person.email }}">✉️</a>{% endif %}</td>
            <td>{{ person.role }}</td>
            <td>{{ person.affiliation }}</td>
            <td>{{ person.focus }}</td>
          </tr>
          {% endfor %}
        </tbody>
      </table>
    </div>
  </div>
  {% endfor %}
</div>

