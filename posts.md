---
title: Posts
layout: default
---

<div class="contain">
    <header class="page-header">
        <h1 class="page-title">{{ page.title }}</h1>
    </header>
    
	{% for post in site.posts %}
		{% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
		{% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %}

		{% if forloop.first %}
	<div>
	<ul class="post-list">
		{% endif %}

	<li>
		<span class="post-meta">{{ post.date | date: "%B %-d, %Y" }}</span>
		<h3 class="post-title">
			<a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
		</h3>
	</li>

		{% if forloop.last %}
	</ul>
		</div>
	{% else %}
		{% if this_year != next_year %}
		</ul>
	</div>
	<div class="year-group">
		<h2 class="posts-subheading" id="{{ next_year }}-ref">{{next_year}}</h2>
		<ul class="post-list">
		{% endif %}
	{% endif %}
	{% endfor %}
</div>