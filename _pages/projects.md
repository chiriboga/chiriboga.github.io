---
layout: default
title: Projects
permalink: /projects/
description: "Some really great projects I have worked on"
menu: true
sort: 3
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
            {% if project.inlist == false %}
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
                            <a href="{{project.link}}" target="_blank" rel="noopener noreferrer">{{project.title}}</a>
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
            {% endif %}
            <!-- end article -->
        {% endfor %}
    </div><!-- end Row -->
</div><!-- end Container -->

<!--
<div class="container">
	<div class="row">
		<div class="col col-12">
			<h4 class="lates-title">More Projects</h4>
		</div>
	</div>
</div>
<div class="container">
	<div class="row">
        {% for project in site.data.projects %}
            {% if project.inlist == true %}
            <div class="col-lg-4 col-md-4 col-sm-4 col-xs-12">
                {% if project.link != "" %}
                    <a href="{{project.link}}" target="_blank" rel="noopener noreferrer"><h4 style="margin-bottom:0">{{project.title}}</h4></a>
                {% else %}
                    <h4 style="margin-bottom:0">{{project.title}}</h4>
                {% endif %}
                <p>{{project.tag}}</p>
            </div>
            {% endif %}
        {% endfor %}
    </div>
</div>
-->