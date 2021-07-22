---
layout: default
title: Art
permalink: /art/
description: "A collection of family art for sale"
menu: true
sort: 4
---
{% include hero-art.html %}
<div class="container">
	<div class="row">
		<div class="col col-12">
			<h4 class="lates-title">Our Family Collections</h4>
		</div>
	</div>
</div>
<div class="container">
	<div class="row">
        {% for project in site.data.artcollections %} {% if project.active %}
            <div class="col col-4 col-m-12">
                <a href="{{project.link}}"><img src="{{project.image}}" alt="{{project.title}}" class="img-fluid"></a>
                <a href="{{project.link}}" style="color:#393e46"><h5 style="padding-top: 10px;text-transform: uppercase;font-size: 16px;">{{project.title}}</h5></a>
            </div>
            {% endif %}
            {% endfor %}
    </div><!-- end Row -->
</div><!-- end Container -->