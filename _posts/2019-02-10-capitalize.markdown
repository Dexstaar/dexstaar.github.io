---
layout: post
title:  "Capitalize"
date:   2019-02-10 00:00:02 +0800
categories: Algorithm
---

## Directions
Write a function that accepts a string.  The function should
capitalize the first letter of each word in the string then
return the capitalized string.
<br/><br/>

## Examples
capitalize('a short sentence') --> 'A Short Sentence'<br/>
capitalize('a lazy fox') --> 'A Lazy Fox'<br/>
capitalize('look, it is working!') --> 'Look, It Is Working!'<br/>
<br/><br/>




## Solution 1
{% highlight javascript %}
function capitalize(str) {
    return str.split(' ').map(elem => {
        return elem[0].toUpperCase() + elem.slice(1, elem.length);
    }).join(' ');
}
{% endhighlight %}

<br/><br/>

## Solution 2
{% highlight javascript %}
function capitalize(str) {
	let result = str[0].toUpperCase();

	for (let i = 1; i < str.length; i++) {
		if (str[i-1] === ' ') {
			result += str[i].toUpperCase();
		} else {
			result += str[i];
		}
	}

	return result;
}
{% endhighlight %}




