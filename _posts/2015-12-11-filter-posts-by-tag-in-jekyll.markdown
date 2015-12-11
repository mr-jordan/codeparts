---
layout: post
title:  "Filter posts by tag in Jekyll"
date:   2015-12-11 21:00:00 +0100
tags: jekyll liquid
---
To create a tag archive page on [Jekyll][jekyll] I added a `tag.html` file in my `_layouts` directory. This file is responsible for listing posts with the given tag. Here&#39;s how it works.

<!--more-->

{% highlight html %}
---
layout: default
---
<div>

  <ul class="post-list">
    {% raw %}
    {% capture tag %}{{ page.title | slugify }}{% endcapture %}

    {% for post in site.posts %}
      {% if post.tags contains tag %}
      <li>
        <p class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</p>
        <h2><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h2>
        {{ post.excerpt }}
        <a href="{{ post.url | prepend: site.baseurl }}" rel="nofollow">Continue reading &rarr;</a>
      </li>
      {% endif %}
    {% endfor %}
    {% endraw %} 
  </ul>

</div>
{% endhighlight %}

First, it gets the selected tag from the page title slugified, then it loops through the site posts and show only those who contain the selected tag.

To use the `tag.html` template is necessary to create a markdown file for each tag. I created `html5.md` and placed it in the `tag` folder, it looks like this.

{% highlight html %}
---
layout: tag
title: html5
---
{% endhighlight %}

Where title is the tag that will be filtered and layout is the `tag.html` template.
[Jekyll][jekyll] will create an HTML file for each tag defined this way. Finally to link the tags from my page footer I did this.

{% highlight html %}
<ul class="site-tags">
  {% raw %}
  {% for tag in site.tags %}
    <li class="tag-link"><a href="{{ '/tag/' | append:tag[0] }}" rel="tag">{{ tag[0] }}</a></li>
  {% endfor %}
  {% endraw %} 
</ul>
{% endhighlight %}

[jekyll]: https://jekyllrb.com/

