---
title: Seminars
permalink: /seminars/
nav: true
nav_order: 4
---

CeDEx China runs a regular Brown Bag seminar series during teaching semesters (typically 12:30–14:00).

{% assign seminar_items = site.data.seminars | sort: "date" | reverse %}

<div class="seminar-timeline mt-4">
{% assign current_year = "" %}
{% for item in seminar_items %}
  {% assign item_year = item.date | date: "%Y" %}
  {% if item_year != current_year %}
    {% assign current_year = item_year %}
  <div class="seminar-year-label">{{ current_year }}</div>
  {% endif %}
  <div class="seminar-entry">
    <div class="seminar-date">{{ item.date | date: "%-d %b" }}</div>
    <div class="seminar-content">
      <div class="seminar-title">{{ item.title }}</div>
      <div class="seminar-speaker">{{ item.speaker }}<span class="seminar-affiliation"> · {{ item.affiliation }}</span></div>
    </div>
  </div>
{% endfor %}
</div>

<style>
.seminar-timeline {
  border-left: 2px solid var(--global-divider-color);
  margin-left: 0.5rem;
}
.seminar-year-label {
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--global-text-color-light);
  margin: 1.5rem 0 0.5rem -0.6rem;
  padding-left: 1rem;
}
.seminar-entry {
  display: flex;
  align-items: baseline;
  gap: 1rem;
  padding: 0.65rem 0 0.65rem 1rem;
  border-bottom: 1px solid var(--global-divider-color);
  margin-left: -1px;
  position: relative;
}
.seminar-entry::before {
  content: '';
  position: absolute;
  left: -5px;
  top: 1.1rem;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: var(--global-theme-color);
}
.seminar-date {
  min-width: 3.8rem;
  font-size: 0.78rem;
  font-weight: 600;
  color: var(--global-theme-color);
  flex-shrink: 0;
}
.seminar-content {
  flex: 1;
}
.seminar-title {
  font-size: 0.9rem;
  font-weight: 600;
  color: var(--global-text-color);
  line-height: 1.35;
}
.seminar-speaker {
  font-size: 0.8rem;
  font-weight: 500;
  color: var(--global-text-color);
  margin-top: 0.15rem;
}
.seminar-affiliation {
  font-weight: 400;
  color: var(--global-text-color-light);
}
</style>