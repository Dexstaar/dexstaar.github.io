---
layout: post
title:  "Reverse String"
date:   2019-02-02 19:55:16 +0800
categories: Programming
---

# Directions
Given a string, return true if the string is a palindrome
or false if it is not.  Palindromes are strings that
form the same word if it is reversed. *Do* include spaces
and punctuation in determining if the string is a palindrome.

# Examples:
palindrome("abba") === true
palindrome("abcdefg") === false

# solution 1
{% highlight javascript %}
function palindrome(str) {
    const reversed = str.split('').reverse().join('');

    return str === reversed;
}
{% endhighlight %}


# solution 2
{% highlight javascript %}
function palindrome(str) {
    return str.split('').every((elem, i) => {
        return elem === str[str.length-i-1];
    });
}
{% endhighlight %}
