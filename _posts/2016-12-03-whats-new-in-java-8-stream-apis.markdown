---
layout: post
title:  "What's new in Java 8: Stream APIs"
date:   2016-12-03 19:55:16 +0800
categories: Programming
---


One more thing that makes Java be closer to functional programming language is stream APIs. "Java.util.stream" package provides functions to control Collections (e.g Array, List, Map) using stream.

Let's suppose there is a Collection composed of integers. If we try to get sum of numbers those are bigger than 10, we write code like below in traditional way. This function looks up every element and add them when it meets the condition.

{% highlight java %}
private long getSumUsingTraditional(Collection<Integer> list) {
    int sum = 0;

    for(int elem: list) {

        if(elem > 10) {
            sum += elem;
        }
    }

    return sum;
}
{% endhighlight %}

On the other hand, this arithmetic operation  can be handled with one line source code if we use a stream API. The below source code indicates that the chain of  process to get sum of particular numbers those meet the condition using filter-map-reduce.

{% highlight java %}
private long getSumUsingStream(Collection<Integer> list) {
    return list.stream().filter(x -> x > 10).mapToInt(x -> x).sum();
}
{% endhighlight %}

As I wrote in the previous article of Java 8: Lambda, it tends to reduce ceremony codes and make them simpler & shorter in modern programming. The progress of every programming language is heading toward reducing ceremony codes with improvement of level of abstraction.

In addition to this, stream APIs also provide automatized parallel processing, which is the biggest advantage of functional programming. Let's assume there are 10 elements in the collection. If we manipulate the elements using iteration, the 10 elements are proceeded one by one in serial order. On the other hand, if we use "parallelStream()", the function itself handles the 10 elements' operation in parallel. For example, if we use dual core cpu, each core handles 5 elements at the same time, so theoretically, it performs twice faster than using iteration.

{% highlight java %}
private long getSumUsingParallelStream(Collection<Integer> list) {
    return list.parallelStream().filter(x -> x > 10).mapToInt(x -> x).sum();
}
{% endhighlight %}

Since the progress of computing speed  that had been doubled every 18 months reached the limit, semiconductor manufacturers abandoned the direction of vertical progress and changed strategy to make the use of multiplex cores. Hence, concurrency or parallel programming is inevitable and functional programming is in the limelight. Java has received a transfusion with new features of 8 while it's behind of this paradigm change and being died slowly as long as it's keep being in the loss of hegemony for paradigm shift.

<br/>
<img src="/assets/IMG_1060.JPG" width="500px">
<br/>
 Napucon 2016 declares the era of reactive and functional programming
<br/><br/>
