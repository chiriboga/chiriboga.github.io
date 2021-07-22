---
layout: default
title: Mind and Meditation
permalink: /mind-meditation
description: "A collection of animated NFT pieces created to help inspire your journey to self-healing and reflection by StrokeDriven"
menu: false
sort: 4
---
{% include hero-meditation.html %}
<div class="container">
	<div class="row">
		<div class="col col-12">
			<h4 class="lates-title">Latest Meditation Art by StrokeDriven</h4>
		</div>
	</div>
</div>
<div class="container">
	<div class="row">
    <script type="text/javascript" src="https://richardchiriboga.com/js/vendors/jquery-3.3.1.min.js"></script>
    <script>
        var apiurl = "https://api.opensea.io/api/v1/assets?collection=mind-meditation&format=json&limit=50&offset=0&order_by=token_id&order_direction=desc";
        $.ajax({
            beforeSend: function(request) {
                request.setRequestHeader("X-API-KEY", 'ab6250b512f84ea592705b94ae3b52d1');
            },
            dataType: "json",
            url: apiurl,
            success: function(data) {
                console.log(data.assets);
                $.each(data.assets, function(i, item) {
                    console.log(item.image_url);
                    $('#results').append('<div class="article"  type-id="item-' + item.token_id + '"><div class="container"><div class="article__wrapper"><a href="' + item.permalink + '" rel="noopener noreferrer" target="_blank" title="' + item.name + '" class="article__image" style="background-image:url(' + item.image_url + ')"></a><div class="article__content"><div class="article-tags"><div class="article-tags__box"><span class="article__tag">Original NFT Artwork</span></div></div><h2 class=article__title><a href="' + item.permalink + '" rel="noopener noreferrer" target="_blank" title="' + item.name + '">' + item.name + '</a></h2><p class="article__excerpt" markdown="1">' + item.description + ' <div class="article__footer"><a href="' + item.permalink + '" rel="noopener noreferrer" target="_blank" title="' + item.name + '" class="read-more">View Artwork <i class="ion ion-ios-arrow-forward"></i></a></div></div></div></div></div>');
                });
            }
        });
    </script>
    <div id="results"></div>
    </div><!-- end Row -->
</div><!-- end Container -->