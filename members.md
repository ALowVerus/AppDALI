---
layout: page
title: Members
permalink: /members.html
---

<div class="container">
	<h1>Members of the DALI Lab</h1>
	<div class="row">
	{% for member in site.data.members %}
		<div class="col-md-3 mx-auto">
			<img src="http://mappy.dali.dartmouth.edu/{{ member.iconUrl }}" class="memberpic">
			<h1>
				{{ member.name }}  
				{% assign lat = member.lat_long[0] | downcase %}
				{% assign long = member.lat_long[1] | downcase %}
				<a href="https://www.google.com/maps/@{{ lat }},{{ long }},18z"> 
					<i class="fas fa-map-marker-alt"></i>
				</a>
				{% if member.url != "" %}
					{% if member.url | 0, 1 == "//" %}
					<a href="http://{{ member.url | 2,-1 }}">
					{% else %}
					<a href="{{ member.url }}">
					{% endif %}
						<i class="fas fa-desktop"></i>
					</a>
				{% endif %}
			</h1>
			<h2>
				{% for term in member.terms_on %}
					{{ term }} 
				{% endfor %}
				{% if member.project != [] %}
					{% for item in member.project %}
						- {{ item }}
					{% endfor %}
				{% endif %}
			</h2>
			<p>{{ member.message }}</p>
			<p>
				
			</p>
		</div>
	{% endfor %}
	</div>
</div>