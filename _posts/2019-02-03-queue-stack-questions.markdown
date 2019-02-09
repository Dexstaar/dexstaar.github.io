---
layout: post
title:  "Queue, Stack & Related Questions"
date:   2019-02-03 00:00:01 +0800
categories: Algorithm
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


