---
layout: post
title:  "Array helpers in JavaScript"
date:   2018-11-01 00:00:01 +0800
categories: Programming
---


There are array helper methods that help us handle array data structure from ES6 in JavaScript.

# foreach

{% highlight javascript %}
var colors = ['red', 'blue', 'green' ];

for (var i=0; i<colors.length; i++) {
  console.log(colors[i]);
}

colors.forEach(color => {
  console.log(color);
});
{% endhighlight %}




# map
{% highlight javascript %}
var numbers = [1,2,3];
var doubledNumbers = [];

for (var i=0; i<numbers.length; i++) {
  doubledNumbers.push(numbers[i] * 2);
}

var doubled = numbers.map(function(number) {
  return number * 2;
});

doubled;
doubledNumbers;
{% endhighlight %}

{% highlight javascript %}
var cars = [
  { model: 'Buick', price: 'CHEAP' },
  { model: 'Camaro', price: 'expensive' }
];

var prices = cars.map(function(car) {
  return car.price;
});

prices;
{% endhighlight %}



# filter

# find

# every

# some

# reduce
