---
layout: post
title:  "Queue, Stack & Related Questions"
date:   2019-02-03 19:55:16 +0800
categories: Programming
---

## Queue
{% highlight javascript %}
class Queue {
  constructor() {
    this.data = [];
  }

  add(record) {
    // Adding a record to the start of array
    this.data.unshift(record);
  }

  remove() {
    return this.data.pop();
  }
}
{% endhighlight %}




