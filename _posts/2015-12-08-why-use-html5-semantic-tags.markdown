---
layout: post
title:  "Why use HTML5 semantic tags?"
date:   2015-12-08 21:00:00 +0100
tags: jekyll html5
---
For my little blog website, I decided to use [Jekyll][jekyll]. It comes with a nice [sample theme][jekyll-new] that uses some of the new HTML5 semantic tags, I decided to keep them and add some more such as `<main>` or `<aside>`. I ended up having something like this.

{% highlight html %}
<body>
  <header class="site-header">
    <a class="site-title" href="/">...</a>
  </header>
  <div class="page-content">
    <main>
      <article>
        <h1>Why use HTML5 semantic tags?</h1>
        <p>...</p>
      </article>
    </main>
    <aside>
      <h2>About</h2>
      <p>...</p>
    </aside>
  </div>
  <footer class="site-footer">
    <ul class="site-tags">...</ul>
    <div class="license">...</div>
  </footer>
</body>
{% endhighlight %}

But why to use semantic tags instead of regular divs?

I decided to use semantic tags because web pages are read by both humans and programs, using these elements helps programs determine the purpose or role of various parts of my web page and this information could be extremely useful to; for example, screen readers or search engines.

[jekyll]: https://jekyllrb.com/
[jekyll-new]: https://github.com/jglovier/jekyll-new
