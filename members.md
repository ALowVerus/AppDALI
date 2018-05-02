---
layout: page
title: Members
permalink: /members.html
---

# members

<div class="row">
{% for member in site.data.members %}
	<div class="col-md-4">
		<div class="card">
			<img src="http://mappy.dali.dartmouth.edu/{{ member.iconUrl }}">
    		<h1>
    			{{ member.terms_on }} - {{ member.name }}
    			{% if member.project != "" %}
    			- {{ member.project }}
    			{% endif %}
    		</h1>
    		<p>{{ member.message }}</p>
    		<p>
    			Find me on Google Maps!
    			<a href="https://www.google.com/maps/@{{ member.lat_long }}"> 
    				Click here!
    			</a>
    		<p>
    		<p>
    			{% if {{ member.url | 0, 1 }} == "//" %}
    			<a href="http://{{ member.url | 2,-1 }}">
    			{% else %}
    			<a href="{{ member.url }}">
    			{% endif %}
    				Click here for my website!
    			</a>
    		</p>
    	</div>
	</div>
{% endfor %}
</div>