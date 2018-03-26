---
layout: post
title:  "OOP and Funational Prgramming in JavaScript"
date:   2018-03-25 19:55:16 +0800
categories: Programming
---

JavaScript has characters of both Object Oriented Programming (OOP) and Functional Programming (FP).


[OOP]

First of all, There are the fetures comes from OOP.

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


- extends







[Functional Programming]

# Map / Reduce / Filter

# Pure Functions


# Immutability


# Higher Order Functions
