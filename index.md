---
title: Home
layout: home
---

<div class="contain">
	<div class="intro">
		<p>Front-end developer focused on CSS, accessibility, and UX.</p>
		<a class="more" href="/about">About</a>
	</div>
	<div class="latest-posts">
		<h2>{% include posts.svg %}Latest Posts</h2>
		<ul class="post-list">
			{% for post in site.posts limit:5 %}
			<li>
				<span class="post-meta">{{ post.date | date: "%B %-d, %Y" }}</span>
				<h3 class="post-title">
					<a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
				</h3>
			</li>
			{% endfor %}
		</ul>
		<a class="more" href="/posts">All Posts</a>
	</div>
	<div class="home-categories">
		<h2>{% include category.svg %}Browse by Category</h2>
		<ul class="categories-list">
			{% for category in site.categories %}
			<li><a href="/category/{{ category[0] | downcase }}">{{ category[0] }} ({{ category | last | size }})</a></li>
			{% endfor %}
		</ul>
	</div>
</div>