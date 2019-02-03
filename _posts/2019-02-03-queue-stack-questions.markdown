---
layout: post
title:  "Queue, Stack & Related Questions"
date:   2019-02-03 19:55:16 +0800
categories: Programming
---


## Queue
{% highlight javascript %}
class Queue {
  constructor() {
    this.data = [];
  }

  add(record) {
    // Adding a record to the start of array
    this.data.unshift(record);
  }

  remove() {
    return this.data.pop();
  }
}
{% endhighlight %}


## Weave
#### Directions
1) Complete the task in weave/queue.js<br/>
2) Implement the 'weave' function.
Weave receives two queues as arguments and combines the contents of each into a new, third queue.
The third queue should contain the *alterating* content of the two queues.  
The function should handlequeues of different lengths without inserting 'undefined' into the new one. <br/>
 *Do not* access the array inside of any queue, only
 use the 'add', 'remove', and 'peek' functions.
#### Example



#### Solution




## Stack



## Queue From Stacks
#### Directions
 Implement a Queue datastructure using two stacks.
 *Do not* create an array inside of the 'Queue' class.
 Queue should implement the methods 'add', 'remove', and 'peek'.
 For a reminder on what each method does, look back
 at the Queue exercise.
#### Examples
{% highlight javascript %}
     const q = new Queue();
     q.add(1);
     q.add(2);
     q.peek();   // returns 1
     q.remove();  // returns 1
     q.remove();  // returns 2
{% endhighlight %}

#### Solution
