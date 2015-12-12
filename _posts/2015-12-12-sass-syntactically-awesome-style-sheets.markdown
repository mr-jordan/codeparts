---
layout: post
title:  "Sass: Syntactically Awesome Style Sheets"
date:   2015-12-12 18:00:00 +0100
tags: jekyll sass css
---
[Jekyll][jekyll] provides built-in support for [Sass][sass], a style sheet language, which includes features that extend the functionality of plain static CSS. These are some of the [Sass][sass] features I used.

<!--more-->

## Variables
The use of variables is useful to keep colors and font sizes consistent throughout the web site.

{% highlight scss %}
$text-color: #333;
$brand-color: #090;

$base-font-size: 16px;
$small-font-size: $base-font-size * 0.875;
{% endhighlight %}

## Nesting
Nesting is good for writing CSS with a clear nested and visual hierarchy.

{% highlight scss %}
.post-list {
  margin-left: 0;
  list-style: none;

  > li {
    margin-bottom: $spacing-unit;
  }

  :last-child {
    margin: 0;
  }
}
{% endhighlight %}

## Partials
Partial [Sass][sass] files contain little snippets of CSS that can be included in other [Sass][sass] files. This is a great way to modularize the CSS, keeping things easier to maintain. 

## Import
[Sass][sass] import can be used to concatenate all partials into a single file. The main benefit of a single style sheet is that it reduces the number of server requests when first loading the page.

{% highlight scss %}
@import
        "base",
        "layout",
        "syntax-highlighting"
;
{% endhighlight %}

## Compression
I take advantage of the file size optimization available with [Sass][sass]. In the `_config.yml` file I added this line to output compressed CSS.

{% highlight yml %}
sass:
  style: compressed
{% endhighlight %}

[jekyll]: https://jekyllrb.com/
[sass]: http://sass-lang.com/

