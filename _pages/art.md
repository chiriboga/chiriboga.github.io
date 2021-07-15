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
			<h4 class="lates-title">Latest Art Pieces</h4>
		</div>
	</div>
</div>
<div class="container">
	<div class="row">
        {% for project in site.data.art %}
            {% if project.active %}
            <!-- begin article loop -->
            <div class="article">
                <div class="container">
                    <div class="article__wrapper">
                    {% if project.link != "" %}
                        <a href="{{project.link}}" title="{{project.title}}" target="_blank" rel="noopener noreferrer" class="article__image" style="background-image: url({{project.image}})"></a>
                    {% else %}
                        <div class="article__image" style="background-image: url({{project.image}})"></div>
                    {% endif %}
                    <div class="article__content ">
                        <div class="article-tags">
                        <div class="article-tags__box">
                            <span class="article__tag">{{project.tag}}</span>
                        </div>
                        </div>
                        <h2 class="article__title">
                        {% if project.link != "" %}
                            <a href="{{project.link}}" title="{project.title}}" target="_blank" rel="noopener noreferrer">{{project.title}}</a>
                        {% else %}
                            {{project.title}}
                        {% endif %}
                        </h2>
                        <p class="article__excerpt">{{project.description}}</p>
                        <div class="article__footer">
                        {% if project.link != "" %}
                            <a href="{{project.link}}" title="{project.title}}" class="read-more" target="_blank" rel="noopener noreferrer">View Artwork <i class="ion ion-ios-arrow-forward"></i></a>
                        {% else %}
                            <span class="read-more">COMING SOON</span>
                        {% endif %}
                        </div>
                    </div>
                    </div>
                </div>
            </div>
            <!-- end article -->
         {% endif %}
        {% endfor %}
    </div><!-- end Row -->
</div><!-- end Container -->