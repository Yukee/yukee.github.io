---
layout: post
title:  "Hello Word!"
date:   2017-07-23 02:25:02 +0200
categories: jekyll update
---

Hello world!
This is my first blog post.
It features one self-referential python program, three sentences -- one of which is self-referential --, and 196 characters.

{% highlight python %}
s = 's = %r\nprint(s%%s)'
print(s%s)
{% endhighlight %}

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
