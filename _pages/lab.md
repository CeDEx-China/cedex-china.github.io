---
title: Lab
permalink: /lab/
nav: true
nav_order: 6
nav_url: https://cedex-china.github.io/cedex-lab/
---

CeDEx Lab studies how people make decisions through controlled experiments.

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
</style>

<ul class="cedex-tabs" id="labTabs" role="tablist">
  <li role="none">
    <button class="cedex-tab-btn active" id="participants-tab" role="tab" aria-selected="true" data-tab="participants" onclick="switchLabTab('participants')">For Participants</button>
  </li>
  <li role="none">
    <button class="cedex-tab-btn" id="experimenters-tab" role="tab" aria-selected="false" data-tab="experimenters" onclick="switchLabTab('experimenters')">For Experimenters</button>
  </li>
</ul>

<div class="cedex-tab-content mt-3" id="labTabContent">

<div class="cedex-panel active" id="participants" role="tabpanel" aria-labelledby="participants-tab" markdown="1">

## Why Join

- Contribute to behavioral and economic research at UNNC
- Sessions run under one hour
- Earn a show-up fee plus performance-based bonuses

## Who Can Participate

Open to all current UNNC students — no background or experience required.

## How to Register

1. Register on ORSEE: [orsee.nottingham.edu.cn](http://orsee.nottingham.edu.cn/public/participant_create.php)
2. Use your official UNNC email address (ending with @nottingham.edu.cn)
3. Activate your account through the confirmation email
4. Enable invitations for both laboratory and internet experiments

## Important Notes

- ORSEE access requires UNNC campus network (campus desktop or eduroam)
- All studies obtain ethics approval before participation
- Data are collected and used anonymously
- Registration does not commit you to any study — you can deregister at any time

For questions, contact [CedexChina@nottingham.edu.cn](mailto:CedexChina@nottingham.edu.cn).

</div>

<div class="cedex-panel" id="experimenters" role="tabpanel" aria-labelledby="experimenters-tab" markdown="1">

## Book the Lab

CeDEx Lab provides a dedicated environment for running controlled experiments at UNNC.

To request a session, submit the booking form below. 

[Request a Session →](https://forms.office.com/r/hLWm2bfuvq){: .btn .btn-sm .btn-outline-primary .mt-2 .mb-3}

For questions, contact [CedexChina@nottingham.edu.cn](mailto:CedexChina@nottingham.edu.cn).

</div>

</div>

<script>
function switchLabTab(tabId) {
  document.querySelectorAll('#labTabs .cedex-tab-btn').forEach(function(btn) {
    btn.classList.remove('active');
    btn.setAttribute('aria-selected', 'false');
  });
  document.querySelectorAll('#labTabContent .cedex-panel').forEach(function(panel) {
    panel.classList.remove('active');
  });
  var activeBtn = document.querySelector('#labTabs [data-tab="' + tabId + '"]');
  var activePanel = document.getElementById(tabId);
  if (activeBtn) {
    activeBtn.classList.add('active');
    activeBtn.setAttribute('aria-selected', 'true');
  }
  if (activePanel) {
    activePanel.classList.add('active');
  }
}
</script>
