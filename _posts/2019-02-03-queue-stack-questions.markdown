---
layout: post
title:  "Queue Stack and related questions"
date:   2019-02-03 19:55:16 +0800
categories: Algorithm
---

## Queue
{% highlight javascript %}
class Queue {
  constructor() {
    this.data = [];
  }

  add(record) {
    this.data.unshift(record);
  }

  remove() {
    return this.data.pop();
  }

  peek() {
    return this.data[this.data.length -1];
  }
}
{% endhighlight %}


