---
layout: post
title:  "OOP and FP in JavaScript"
date:   2018-03-25 19:55:16 +0800
categories: Programming
---

JavaScript has characters of both Object Oriented Programming (OOP) and Functional Programming (FP).


[OOP]

First of all, There are the features come from OOP.

# Objects
Better knowns as classes in most OOP and functions in JS.
 Objects can be thought of as the main actors in an application, or simply the main “things” or building blocks that do all the work.
As you know by now, objects are everywhere in JavaScript since every component in JavaScript is an Object, including Functions, Strings, and Numbers.
We normally use object literals or constructor functions to create objects.




# Encapsulation
Encapsulation refers to enclosing all the functionalities of an object within that object so that the object’s internal workings (its methods and properties) are hidden from the rest of the application. This allows us to abstract or localize specific set of functionalities on objects.




# Inheritance
Inheritance refers to an object being able to inherit methods and properties from a parent object.
In JavaScript, this inheritance has been implemented using prototype and extends (ES6).



- prototype

https://medium.com/@bluesh55/javascript-prototype-이해하기-f8e67c286b67

{% highlight javascript %}
function Person() {
  this.eyes = 2;
  this.nose = 1;
}
var kim  = new Person();
var park = new Person();
console.log(kim.eyes);  // => 2
console.log(kim.nose);  // => 1
console.log(park.eyes); // => 2
console.log(park.nose); // => 1
{% endhighlight %}

kim과 park은 eyes와 nose를 공통적으로 가지고 있는데, 메모리에는 eyes와 nose가 두 개씩 총 4개 할당됩니다. 객체를100개 만들면 200개의 변수가 메모리에 할당되겠죠?
바로 이런 문제를 프로토타입으로 해결할 수 있습니다.

{% highlight javascript %}
function Person() {}
Person.prototype.eyes = 2;
Person.prototype.nose = 1;
var kim  = new Person();
var park = new Person():
console.log(kim.eyes); // => 2
...
{% endhighlight %}


자바스크립트에는 Prototype Link 와 Prototype Object라는 것이 존재합니다. 그리고 이 둘을 통틀어 Prototype이라고 부릅니다.


- extends







[Functional Programming]

# Map / Reduce / Filter

# Pure Functions


# Immutability


# Higher Order Functions
