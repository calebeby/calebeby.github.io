---
layout: default
title: "Home"
permalink: /
---
<div class="row">
<div class="about hide-on-small-only col m4 card">
  hello.
</div>
<div class="posts col s12 m8">
  {% for post in site.posts %}
	<a href="{{ post.url }}" title="{{ post.title }}">
		<div class="card hoverable waves-effect waves-block waves-light blog-post">
			<div class="card-image">
				<img class="responsive-img" src="/assets{{ post.url }}cover.jpg">
        <span class="card-title white-text">{{ post.title }}</span>
			</div>
			<div class="card-content">
				{% if post.date %}
					<span class="chip small">
						<i class="mdi mdi-calendar"></i>
						<time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">
							{{ post.date | date: "%B %-d, %Y" }}
						</time>
					</span>
				{% endif %}
				{% for tag in post.tags %}<a href="/tags/{{ tag }}" class="chip small"><i class="mdi mdi-tag"></i>{{ tag }}</a>{% endfor %}
			</div>
		</div>
	</a>
  {% endfor %}
  </div>
</div>
