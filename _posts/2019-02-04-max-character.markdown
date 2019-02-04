---
layout: post
title:  "Max Character"
date:   2019-02-04 19:55:16 +0800
categories: Programming
---

#### Directions
 Given a string, return the character that is most commonly used in the string.
#### Examples
maxChar("abcccccccd") === "c"<br/>
maxChar("apple 1231111") === "1"<br/>



#### solution
{% highlight javascript %}
function maxChar(str) {
  const charMap = {};
  let max = 0;
  let maxChar = "";

  for(const char of str) {
    if(charMap[char]) {
      charMap[char]++;
    } else {
      charMap[char] = 1;
    }
  }

  for(let char in charMap) {
    if(charMap[char] > max) {
      max = charMap[char];
      maxChar = char;
    }
  }

  return maxChar;
}
{% endhighlight %}
