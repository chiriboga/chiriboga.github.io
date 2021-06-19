---
layout: default
title: Projects
permalink: /projects/
description: "Some really great projects I have worked on"
---
{% include hero-projects.html %}
<div class="container">
	<div class="row">
		<div class="col col-12">
			<h4 class="lates-title">Latest Projects</h4>
		</div>
	</div>
</div>
<div class="container">
	<div class="row">
        {% for project in site.data.projects %}
            <!-- begin article loop -->
            <div class="article">
                <div class="container">
                    <div class="article__wrapper">
                    {% if project.link != "" %}
                        <a href="{{project.link}}" target="_blank" rel="noopener noreferrer" class="article__image" style="background-image: url({{project.image}})"></a>
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
                            <a href="/2021/06/01/virtual-drupal-nyc-meetup/" target="_blank" rel="noopener noreferrer">{{project.title}}</a>
                        {% else %}
                            {{project.title}}
                        {% endif %}
                        </h2>
                        <p class="article__excerpt">{{project.description}}</p>
                        <div class="article__footer">
                        {% if project.link != "" %}
                            <a href="{{project.link}}" class="read-more" target="_blank" rel="noopener noreferrer">View Website <i class="ion ion-ios-arrow-forward"></i></a>
                        {% endif %}
                        </div>
                    </div>
                    </div>
                </div>
            </div>
            <!-- end article -->
        {% endfor %}
    </div><!-- end Row -->
</div><!-- end Container -->