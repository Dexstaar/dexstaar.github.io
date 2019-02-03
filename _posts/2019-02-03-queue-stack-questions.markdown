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
{% highlight javascript %}
    const queueOne = new Queue();
    queueOne.add(1);
    queueOne.add(2);
    const queueTwo = new Queue();
    queueTwo.add('Hi');
    queueTwo.add('There');
    const q = weave(queueOne, queueTwo);
    q.remove()  1
    q.remove()  'Hi'
    q.remove()  2
    q.remove()  'There'
{% endhighlight %}

#### Solution
{% highlight javascript %}
function weave(sourceOne, sourceTwo) {
    let weaved = new Queue();

    while(sourceOne.peek() || sourceTwo.peek()) {
        if(sourceOne.peek()) weaved.add(sourceOne.remove());
        if(sourceTwo.peek()) weaved.add(sourceTwo.remove());
    }

    return weaved;
}
{% endhighlight %}



## Stack
{% highlight javascript %}
class Stack {
	constructor() {
		this.data = [];
	}

	push(record) {
		this.data.push(record);
	}

	pop() {
		return this.data.pop();
	}

	peek() {
		return this.data[this.data.length - 1];
	}
}
{% endhighlight %}


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
{% highlight javascript %}
constructor() {
    this.main = new Stack();
    this.sub = new Stack();
  }

  add(element) {
    while (this.main.peek()) {
      this.sub.push(this.main.pop());
    }

    this.main.push(element);

    while (this.sub.peek()) {
      this.main.push(this.sub.pop());
    }
  }

  remove() {
    return this.main.pop();
  }

  peek() {
    return this.main.peek();
  }
{% endhighlight %}