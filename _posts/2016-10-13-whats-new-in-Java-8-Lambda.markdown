---
layout: post
title:  "What's new in Java 8: Lambda"
date:   2016-10-13 19:55:16 +0800
categories: Programming
---

It seems little late to talk about new features in Java 8 at this point of time, it's been already 2 years since it's released and people are talking about Java 9. There are 2 types of Java developers either who are interested and studying 8 but still not using it in production environment or already switched to Scala in response to the necessity of functional programming when I was talking to people in Java related meetups here in Singapore. Due to the late response of changing world, Java 8 seems to be hanging, able to be neither. It's treated like a subject of study for late adapters or an obsolete one for early functional programming adapters.

I also didn't catch up the new features of Java because I didn't use it in my previous company and tried to learn a different language. But I can't avoid it anymore because I still choose it as a primary language when I participate in Coding test.



# Introduction to Lambda

Lambda is not very familiar but also not a totally new one for me. When I was coding with C#, I saw a strange mark "=>" and founded and it's called Lambda on the internet (It's used like "->" in Java). But I couldn't understand it and didn't try to figure out very much at that time. Since it became the hottest topic of 8, let's look at it more carefully this time.

First of all, let's define an interface class.

{% highlight java %}
interface Calculator {
    int calculate(int first, int second);
}
{% endhighlight %}

There is a method named calculate, that will do something with input parameters first and second. But action of the method is not implemented because it's an interface. This's called an abstract method, and if there is one abstract method in a interface class, we call it functional interface. Lambda is a way to implement action of this kind of abstract method when this kind of functional interface is called.

{% highlight java %}
class Operator {
    public void operate(Calculator calculator){
        int result = calculator.calculate(2,3);
        System.out.println(result);
    }
}
{% endhighlight %}

Then, there is a class named Operator. And the method name operate calls calculate in Calculator then print the return value.

{% highlight java %}
public class Lambda {
    public static void main(String[] args){
        Operator operator = new Operator();

        // traditional way
        operator.operate(new Calculator(){
            public int calculate(int first, int second){
                return first + second;
            }
        });

        // using Lambda
        operator.operate( (first, second) -> {
            return first * second;
        });
    }
}
{% endhighlight %}

Now, execute the operate method in the main method. When the operate method is called, it calls the caculate method, which is an abstract, so the action should be implemented. In previous Java versions under 8, constructs Calculator, and write all words that requires following calculate methods, then I can write action within {}.



{% highlight java %}
        // traditional way
        operator.operate(new Calculator(){
            public int calculate(int first, int second){
                return first + second;
            }
        });
{% endhighlight %}

On the contrary, the code can be much more simplified if I use Lambda expression.

{% highlight java %}
        // using Lambda
        operator.operate( (first, second) -> {
            return first * second;
        });
{% endhighlight %}

The existing code only to follow formality, which is  so called boilerplate or ceremony code, is removed such as "new Calculator()" and "public int calculate". And there are only required parameters and actions within {}. The trend of modern programming language is removing this kind of ceremony code due to it hinders productivity and quality of computer programming.

It became a long explanation just with Lambda. Other features will be continued next time...
