---
layout: post
title:  "Queue, Stack & Related Questions"
date:   2019-02-03 19:55:16 +0800
categories: Programming
---


## Queue
aaa
{% highlight javascript %}
class Queue {
  constructor() {
    this.data = [];
  }

  add(record) {
    // Adding a record to the end of array
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



# Directions
Given a string, return a new string with the reversed order of characters

# Examples
reverse('apple') === 'leppa' <br/>
reverse('hello') === 'olleh' <br/>
reverse('Greetings!') === '!sgniteerG'

# solution 1
{% highlight javascript %}
function reverse(str) {
  let reversed = '';

  str.split('').forEach(elem => {
    reversed = elem + reversed;
  });

  return reversed;
}
{% endhighlight %}

# solution 2
{% highlight javascript %}
function reverse(str) {
  return str.split('').reverse().join('');
}
{% endhighlight %}

# solution 3
{% highlight javascript %}
function reverse(str) {
  return str.split('').reduce((acc, elem) => {
    return elem + acc;
  }, '');
}
{% endhighlight %}


