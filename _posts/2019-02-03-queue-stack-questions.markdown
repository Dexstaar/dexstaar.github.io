---
layout: post
title:  "Queue, Stack & Related Questions"
date:   2019-02-03 19:55:16 +0800
categories: Programming
---

## Queue
{% highlight %}
class Car {
  constructor({title}) {
    this.title = title;
  }

  drive() {
    return 'vroom';
  }
}

const car = new Car({ title: 'Toyota' });
console.log(car);
console.log(car.drive());
{% endhighlight %}


