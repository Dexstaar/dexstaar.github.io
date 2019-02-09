---
layout: post
title:  "Queue, Stack & Related Questions"
date:   2019-02-03 00:00:01 +0800
categories: Algorithm
---

## Queue
{% highlight javascript %}
function Car(options) {
  this.title = options.title;
}

Car.prototype.drive = function() {
  return 'vroom';
}

const car = new Car({ title: 'Focus' });

console.log(car.drive());
console.log(car);
{% endhighlight %}


