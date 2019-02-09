---
layout: post
title:  "Queue, Stack & Related Questions"
date:   2019-02-09 00:00:01 +0800
categories: Algorithm
---

## Note
There is a bug on either Github page or Jekyll. It causes a build error if you write "## Queue" from the beginning of the post.

## Queue
{% highlight %}
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
		return this.data[this.data.length - 1];
	}
}
{% endhighlight %}