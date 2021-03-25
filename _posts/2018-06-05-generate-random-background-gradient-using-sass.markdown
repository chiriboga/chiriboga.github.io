---
layout: post
title:  "Generate Random Background Gradient using SASS"
date:   2018-06-05 10:00:00 -0500
image:  'blog/background-gradient.png'
tags:   CSS
---
I thought it would be a cool idea to be able to create a mixin for adding gradient backgrounds to an element. Then I thought, what if I could create one that would output the gradient without knowing what the initial color was. So the following code first creates a random hex color and creates the proper options. You can either create a light to dark version:
- **light** (lighten 15% of the initial color)
- **lightest** (lighten 30% of the initial color)
- **dark** (darken 15% of the initial color)
- **darkest** (darken 30% of the initial color)

``` scss
$s-min: 20;
$s-max: 70;
$l-min: 30;
$l-max: 90;
$random-color: hsl(random(360),$s-min+random($s-max+-$s-min),$l-min+random($l-max+-$l-min));

@mixin linearGradient($color,$type) {
  $to: (
    light: lighten($color,15%),
    lightest: lighten($color,30%),
    dark: darken($color,15%),
    darkest: darken($color,30%)
  );
  
  font-family:$type;
  color: $color;
  background: nth(nth($color, 1), 1);
  background: -webkit-linear-gradient(legacy-direction($color),map-get($to, $type));
  background: linear-gradient($color,map-get($to, $type));
}


.selector {
  @include linearGradient($random-color,light);
}
```

You can create the gradient by either putting in your own color or using the **$random-color** variable followed by how you would like to see the background created. I will probably add more to this later, but for now the gradient is linear. 

### Output

``` css
.selector {
  font-family: light;
  color: #5eb8cf;
  background: #5eb8cf;
  background: -webkit-linear-gradient(legacy-direction(#5eb8cf), #99d2e1);
  background: linear-gradient(#5eb8cf, #99d2e1);
}
```

You can also check out the CodePen example below.
<p data-height="400" data-theme-id="0" data-slug-hash="aKNXbm" data-default-tab="css,result" data-user="chiriboga" data-embed-version="2" data-pen-title="aKNXbm" class="codepen">See the Pen <a href="https://codepen.io/chiriboga/pen/aKNXbm/">aKNXbm</a> by Richard Chiriboga (<a href="https://codepen.io/chiriboga">@chiriboga</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>