---
title: People
permalink: /people/
nav: true
nav_order: 2
---

CeDEx China brings together researchers, faculty members, and lab management with expertise in behavioural and experimental economics.

<style>
.cedex-tabs {
  display: flex;
  flex-wrap: wrap;
  gap: 0.25rem;
  margin-top: 1.5rem;
  border-bottom: 2px solid var(--global-divider-color, #e0e0e0);
  padding-bottom: 0;
  list-style: none;
  padding-left: 0;
}
.cedex-tabs li {
  margin-bottom: -2px;
}
.cedex-tab-btn {
  display: inline-block;
  padding: 0.5rem 1.1rem;
  font-size: 0.85rem;
  font-weight: 500;
  color: var(--global-text-color-light, #777);
  cursor: pointer;
  border: 2px solid transparent;
  border-bottom: none;
  border-radius: 6px 6px 0 0;
  transition: all 0.2s ease;
  user-select: none;
  background: transparent;
  text-decoration: none;
}
.cedex-tab-btn:hover {
  color: var(--global-theme-color, #b509ac);
  background: rgba(0,0,0,0.03);
}
.cedex-tab-btn.active {
  color: var(--global-theme-color, #b509ac);
  border-color: var(--global-divider-color, #e0e0e0);
  border-bottom-color: var(--global-bg-color, #fff);
  background: var(--global-bg-color, #fff);
}
.cedex-panel {
  display: none;
  margin-top: 1.5rem;
}
.cedex-panel.active {
  display: block; 
}
.cedex-person-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 1rem;
}
.cedex-person-card {
  border: 1px solid var(--global-divider-color, #e0e0e0);
  border-radius: 8px;
  padding: 1rem 1.1rem;
}
.cedex-person-name {
  font-weight: 600;
  font-size: 0.9rem;
  margin: 0 0 0.2rem;
}
.cedex-person-role {
  font-size: 0.78rem;
  font-weight: 500;
  color: var(--global-theme-color, #b509ac);
  margin: 0 0 0.15rem;
}
.cedex-person-affil {
  font-size: 0.78rem;
  color: var(--global-text-color-light, #777);
  margin: 0 0 0.15rem;
}
.cedex-person-focus {
  font-size: 0.78rem;
  color: var(--global-text-color, #333);
  margin: 0;
}
</style>

<ul class="cedex-tabs" role="tablist">
  {% for section in site.data.people %}
  {% assign tab_id = section.group | slugify %}
  <li role="none">
    <button class="cedex-tab-btn {% if forloop.first %}active{% endif %}"
            id="{{ tab_id }}-tab"
            role="tab"
            aria-selected="{% if forloop.first %}true{% else %}false{% endif %}"
            data-tab="{{ tab_id }}"
            onclick="switchPeopleTab('{{ tab_id }}')">
      {{ section.group }}
    </button>
  </li>
  {% endfor %}
</ul>

{% for section in site.data.people %}
{% assign tab_id = section.group | slugify %}
<div class="cedex-panel {% if forloop.first %}active{% endif %}" id="{{ tab_id }}" role="tabpanel" aria-labelledby="{{ tab_id }}-tab">
  <div class="cedex-person-grid">
    {% for person in section.members %}
    <div class="cedex-person-card">
      <p class="cedex-person-name">
        {{ person.name }}{% if person.email %}&nbsp;<a href="mailto:{{ person.email }}" title="{{ person.email }}" style="font-size:0.85em;">✉️</a>{% endif %}
      </p>
      <p class="cedex-person-role">{{ person.role }}</p>
      <p class="cedex-person-affil">{{ person.affiliation }}</p>
      {% if person.focus %}
      <p class="cedex-person-focus">{{ person.focus }}</p>
      {% endif %}
    </div>
    {% endfor %}
  </div>
</div>
{% endfor %}

<script>
function switchPeopleTab(tabId) {
  document.querySelectorAll('.cedex-tab-btn').forEach(function(btn) {
    btn.classList.remove('active');
    btn.setAttribute('aria-selected', 'false');
  });
  document.querySelectorAll('.cedex-panel').forEach(function(p) {
    p.classList.remove('active');
  });
  var tabBtn = document.getElementById(tabId + '-tab');
  var panel = document.getElementById(tabId);
  if (tabBtn) {
    tabBtn.classList.add('active');
    tabBtn.setAttribute('aria-selected', 'true');
  }
  if (panel) {
    panel.classList.add('active');
  }
  history.replaceState(null, '', '#people-' + tabId);
}
// Restore tab on page load if hash is present
(function() {
  var hash = location.hash.replace('#people-', '');
  if (hash && document.getElementById(hash + '-tab')) {
    switchPeopleTab(hash);
  }
})();
</script>