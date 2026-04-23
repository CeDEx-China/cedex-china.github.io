---
title: People
permalink: /people/
nav: true
nav_order: 2
---

CeDEx China brings together researchers, faculty members, and lab management with expertise in behavioural and experimental economics.

{% for section in site.data.people %}
### {{ section.group }}

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
			<td>{{ person.name }}</td>
			<td>{{ person.role }}</td>
			<td>{{ person.affiliation }}</td>
			<td>{{ person.focus }}</td>
		</tr>
		{% endfor %}
	</tbody>
</table>

{% endfor %}

For updates to membership, edit _data/people.yml in the repository.
