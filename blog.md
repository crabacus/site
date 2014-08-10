---
layout: page
title: Blog
permalink: /blog/
description: "This is where I post music that isn't finished, or that I'm currently working on. Or I might post random crap too."
excerpt_separator: ""
icon: fa-book
---

<ul class="posts">
	{% for post in site.categories.blog %}
	<li class="item">
		<span class="date">
			<i class="fa fa-calendar"></i>
			{{ post.date | date: "%b %-d, %Y" }}
		</span>
		{{ post.content }}
		<ul class="files">
			{% for file in post.files %}
			{% for f in site.data.music.files %}
				{% if f.file == file %}
					{% assign filepath = f.path %}
				{% endif %}
			{% endfor %}
			<li><a href="{{ filepath }}{{ file }}"><i class="fa fa-file"></i>{{ file }}</a></li>
			{% endfor %}
		</ul>
	</li>
	{% endfor %}
</ul>

<!-- <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>
 -->