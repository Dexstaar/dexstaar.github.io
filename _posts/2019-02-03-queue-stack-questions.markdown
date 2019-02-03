---
layout: post
title:  "Queue, Stack & Related Questions"
date:   2019-02-03 19:55:16 +0800
categories: Programming
---

## Queue
{% highlight javascript %}
class Car {
  constructor({title}) {
    this.title = title;
  }

  drive() {
    return 'vroom';
  }
}

class Toyota extends Car {
  constructor(options) {
    super(options);
    this.color = options.color;
  }

  honk() {
    return 'beep';
  }
}

const toyota = new Toyota({ color: 'red', title: 'Daily Driver' });

console.log(toyota);
console.log(toyota.honk());
console.log(toyota.drive());
{% endhighlight %}


