---
layout: post
title:  "Algorithm for Fibonacci"
date:   2016-11-15 19:55:16 +0800
categories: Programming
---


Recently I attended an online coding test. I was pretty confident with it because practiced algorithm for a couple of month but when I received the question, it looked quite complicated at first. A few minutes later, I realized that it is a kind of fibonacci question. I'll make an example with a typical fibonacci because I am not allowed to reveal the question.

Fibonacci is a combination of numbers with sum of two previous elements;
{% highlight java %}
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, ……..
{% endhighlight %}

The sequence Fn of Fibonacci numbers is defined by the recurrence relation.

{% highlight java %}
Fn = Fn-1 + Fn-2
{% endhighlight %}

The simplest way to solve fibonacci question is using recursion. If I write the answer in Java;

{% highlight java %}
public class Recursion {
    public int fibonacci(int n) {
        if(n <= 1) return n;
        return fibonacci(n-1) + fibonacci(n-2);
    }
}
{% endhighlight %}

The answer that I submitted was similar to the example because the core part of the algorithm was getting sum of fibonacci numbers. I had little doubt it's not adequate if I considered the purpose of coding test but couldn't find any other aspect and just thought maybe they are desperate to hire developers. Then I just found I made a huge mistake because the expected time complexity is O(logN). When I was running test cases with huge number of n, it returned stack over flow error and thought it's kind of primitive problem and obsessed to finding proper primitive type and couldn't think about it's caused by time complexity. The fibonacci function when using recursion is O(2^N).

If required time complexity is O(N), we can solve it using dynamic programming.

{% highlight java %}
public class DynamicProgramming {
    public int fibonacci(int n) {
        int[] arr = new int[n+1];

        arr[0] = 0;
        arr[1] = 1;

        for(int i=2; i<=n; i++) {
            arr[i] = arr[i-1] + arr[i-2];
        }

        return arr[n];
    }
}
{% endhighlight %}

These two methods are either I've practiced or at least heard how I solve fibonacci questions. I couldn't even think about using dynamic programming for having lower time complexity because I was too obsessed to the question. It's shame on me that I submitted with the worst time complexity among well-known algorithms.

By the way, how can I implement of fibonacci with time complexity O(logN)? Honestly, I wasn't even aware of that there is another way to implement fibonacci with lower time complexity. But we can have lower time complexity if we use power of the matrix.

The first 4 elements of fibonacci can be indicated as the matrix;

<img src="/assets/screen-shot-2016-11-15-at-3-57-19-pm.png" width="500px">
<br/>





Then, the matrix to the power of n is;

screen-shot-2016-11-15-at-4-10-01-pm







We can implement fibonacci with time complexity O(N) like below.









Let's squeeze little bit more. This method can be optimized to work in O(logN) time complexity. We can do recursive multiplication to get matrixPower(int[][] arrA, int n) in the previous method.

This idea comes from the fomula;

screen-shot-2016-11-15-at-4-38-57-pm

Therefore the matrix can be;

screen-shot-2016-11-15-at-4-39-50-pm

Keeping dividing with half(n/2) until n became 1, then we can get Fn from the matrix. The upper fomula is when n is even, and the under fomula is used when n is odd because of loosing 1 when n is divided by 2.

screen-shot-2016-11-15-at-4-51-32-pm

This can be expressed using Java code;



So this is what I should have submitted. One thing that consolable is I couldn't have written it even if I had been aware of the time complexity requirement. I was given an hour for the test but it actually took several hours to understand this linear algebra way. But I regret that I was overestimated my knowledge of algorithm. Practicing algorithm is a kind of daily work-out for programmers and I feel I've been getting more confident for programming since I started practicing it. Failures of coding test always gets me frustrated and have a doubt whether I should keep spending time for it.  I totally fucked up my last promising chance in Singapore. Now it's time to go back to the basement and reorganize myself to make new plans for life.
