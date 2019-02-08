---
layout: post
title:  "Reverse String / Integer"
date:   2019-02-02 19:55:16 +0800
categories: Altorithm
---

## Reverse String

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
<br/><br/><br/><br/>


## Reverse Integer
#### Directions
Given an integer, return an integer that is the reverse ordering of numbers.
#### Examples
{% highlight javascript %}
reverseInt(15) === 51
reverseInt(981) === 189
reverseInt(500) === 5
reverseInt(-15) === -51
reverseInt(-90) === -9
{% endhighlight %}

#### Solution
{% highlight javascript %}
function reverseInt(n) {
    const reversed = n.toString().split('').reverse().join('');

    return parseInt(reversed) * Math.sign(n);
}
{% endhighlight %}