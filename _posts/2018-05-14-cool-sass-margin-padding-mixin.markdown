---
layout: post
title:  "Cool SASS Margin and Padding Mixin"
date:   2018-05-14 15:10:47 -0500
image:  'blog/sass.png'
tags:   css
---
So I have recently really gotten into SASS and how powerful it is. I mean I have used it before but nothing like I have in the last couple of weeks. Real world examples are always the best; Especially when you have a more experienced developer helping. 

### Margin and Padding
I have done this for as long as I can remember. I will do margin-top, margin-bottom, padding-top, padding-bottom and I usually do 5, 10, 15, 20, etc. This makes it so easy for me to do this. 

``` scss
$sides: ("b": "bottom","t": "top");
@each $prefix, $value in $sides {
  $property: if($prefix == '', '', -#{$value});
  @for $i from 0 through 10 {
    .m#{$prefix}{
      &#{($i * 5)} {
        margin#{$property}:#{($i * 5)}px;
      }
    }
    .p#{$prefix}{
      &#{($i * 5)} {
        padding#{$property}:#{($i * 5)}px;
      }
    }
  }
}
```


And what you get is this: Note that each one would be rendered __not__ the "TO"

``` css
.mb0{margin-bottom:0px} TO .mb50{margin-bottom:50px}
.mt0{margin-top:0px} TO .mt50{margin-top:50px}
.pb0{padding-bottom:0px} TO .pb50{padding-bottom:50px}
.pt0{padding-top:0px} TO .pt50{padding-top:50px}
```

You can also check out the CodePen example below.
<p data-height="400" data-theme-id="0" data-slug-hash="gzBxvP" data-default-tab="css,result" data-user="chiriboga" data-embed-version="2" data-pen-title="Margins and Padding" class="codepen">See the Pen <a href="https://codepen.io/chiriboga/pen/gzBxvP/">Margins and Padding</a> by Richard Chiriboga (<a href="https://codepen.io/chiriboga">@chiriboga</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>