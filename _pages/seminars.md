---
title: Seminars
permalink: /seminars/
nav: true
nav_order: 4
---

CeDEx China runs a regular Brown Bag seminar series during teaching semesters (typically 12:30-14:00).

## Recent Seminars

{% assign seminar_items = site.data.seminars | sort: "date" | reverse %}

<div class="table-responsive">
<table class="table table-sm table-striped">
	<thead>
		<tr>
			<th>Date</th>
			<th>Speaker</th>
			<th>Affiliation</th>
			<th>Title</th>
		</tr>
	</thead>
	<tbody>
		{% for item in seminar_items %}
		<tr>
			<td>{{ item.date | date: "%-d %B %Y" }}</td>
			<td>{{ item.speaker }}</td>
			<td>{{ item.affiliation }}</td>
			<td>{{ item.title }}</td>
		</tr>
		{% endfor %}
	</tbody>
</table>
</div>

To update this table, edit _data/seminars.yml in the repository.
