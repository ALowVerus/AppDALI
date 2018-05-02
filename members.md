---
layout: page
title: Members
permalink: /members.html
---

# members

<div class="row">
{% for member in site.data.members %}
	<div class="col-md-4">
		<img src="http://mappy.dali.dartmouth.edu/{{ member.iconUrl }}" class="memberpic">
		<h1>{{ member.name }}</h1>
		<h2>
			{% for term in member.terms_on %}
				{{ term }} 
			{% endfor %}
			-
			{% if member.project != [""] %}
				{% for item in project %}
					{{ item }}
				{% endfor %}
			{% endif %}
		</h2>
		<p>{{ member.message }}</p>
		<p>
			Find me on Google Maps!
			{% assign lat = member.lat_long[0] | downcase %}
			{% assign long = member.lat_long[1] | downcase %}
			<a href="https://www.google.com/maps/@{{ lat }},{{ long }},18z"> 
				<i class="fas fa-map-marker-alt"></i>
			</a>
		</p>
		{% if member.url != "" %}
			<p>
				{% if member.url | 0, 1 == "//" %}
				<a href="http://{{ member.url | 2,-1 }}">
				{% else %}
				<a href="{{ member.url }}">
				{% endif %}
					<i class="fas fa-desktop"></i>
				</a>
			</p>
		{% endif %}
	</div>
{% endfor %}
</div>