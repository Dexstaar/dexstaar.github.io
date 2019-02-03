---
layout: post
title:  "Queue, Stack & Related Questions"
date:   2019-02-03 19:55:16 +0800
categories: Programming
---

## Queue
{% highlight javascript %}
function reverse(str) {
  return str.split('').reduce((acc, elem) => {
    return elem + acc;
  }, '');
}
{% endhighlight %}


