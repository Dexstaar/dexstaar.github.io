---
layout: post
title:  "Linked List & Related Questions"
date:   2019-02-10 00:00:02 +0800
categories: Algorithm
---

## Linked List


#### Linked List functions
{% highlight javascript %}
class Node {
  constructor(data, next = null) {
    this.data = data;
    this.next = next;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
  }

  insertFirst(data) {
    this.head = new Node(data, this.head);

    // Or this can be implemented by reusing of insertAt
    // this.insertAt(data, 0);
  }

  size() {
    let counter = 0;
    let node = this.head;

    while(node) {
      counter++;
      node = node.next;
    }

    return counter;
  }

  getFirst() {
    return this.head;

    // Or this can be implemented by reusing of getAt
    // return this.getAt(0);

  }

  getLast() {
    if (!this.head) return null;

    let node = this.head;

    while(node.next) {
      node = node.next;
    }

    return node;


    // Or this can be implemented by reusing of getAt
    // return this.getAt(this.size() - 1);
  }

  clear() {
    this.head = null;
  }

  removeFirst() {
    if(!this.head) return;
    this.head = this.head.next;
  }

  removeLast() {
    if (!this.head) {
      return;
    }

    if (!this.head.next) {
      this.head = null;
      return;
    }

    let previous = this.head;
    let node = this.head.next;

    while (node.next) {
      previous = node;
      node = node.next;
    }

    previous.next = null;
  }

  insertLast(data) {
    const last = this.getLast();

    if (last) {
      // There are some existing nodes in our chain
      last.next = new Node(data);
    } else {
      // The chain is empty!
      this.head = new Node(data);
    }
  }

  getAt(index) {
    if (!this.head) { return null; }

    let counter = 0;
    let node = this.head;

    while(node) {
      if (counter === index) {
        return node;
      }

      counter++;
      node = node.next;
    }

    return null;
  }

  removeAt(index) {
    if (!this.head) { return; }

    if (index === 0) {
      this.head = this.head.next;
      return;
    }

    const previous = this.getAt(index - 1);
    if(!previous || !previous.next) {
      return;
    }
    previous.next = previous.next.next;
  }

  insertAt(data, index) {
    if (!this.head) {
      this.head = new Node(data);
      return;
    }

    if (index === 0) {
      this.head = new Node(data, this.head);
      return;
    }

    const previous = this.getAt(index - 1) || this.getLast();
    const node = new Node(data, previous.next);
    previous.next = node;
  }

  forEach(fn) {
    let node = this.head;
    let counter = 0;

    while (node) {
      fn(node, counter);
      node = node.next;
      counter++;
    }
  }

  *[Symbol.iterator]() {
    let node = this.head;
    while (node) {
      yield node;
      node = node.next;
    }
  }
}
{% endhighlight %}

<br/><br/>


## Mid Point
#### Directions
Return the 'middle' node of a linked list.
If the list has an even number of elements, return
the node at the end of the first half of the list.
*Do not* use a counter variable, *do not* retrieve
the size of the list, and only iterate
through the list one time. <br/>
#### Example
const l = new LinkedList();<br/>
l.insertLast('a');<br/>
l.insertLast('b');<br/>
l.insertLast('c');<br/>
midpoint(l); // returns { data: 'b' } <br/>

#### Solution
{% highlight javascript %}
function midpoint(list) {
    let slow = list.getFirst();
    let fast = list.getFirst();

    while (fast.next && fast.next.next) {
        slow = slow.next;
        fast = fast.next.next;
    }

    return slow;
}
{% endhighlight %}


<br/><br/>


## Circular
#### Directions
Given a linked list, return true if the list
is circular, false if it is not.
#### Examples
const l = new List(); <br/>
const a = new Node('a'); <br/>
const b = new Node('b');<br/>
const c = new Node('c');<br/>
l.head = a;<br/>
a.next = b;<br/>
b.next = c;<br/>
c.next = b;<br/>
circular(l) // true<br/>

#### Solution
{% highlight javascript %}
function circular(list) {
    let slow = list.getFirst();
    let fast = list.getFirst();

    while(fast.next && fast.next.next) {
        slow = slow.next;
        fast = fast.next.next;

        if(slow === fast) return true;
    }

    return false;
}
{% endhighlight %}