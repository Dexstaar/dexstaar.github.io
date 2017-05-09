---
layout: post
title:  "What's new in Java 8: Lambda"
date:   2016-10-13 19:55:16 +0800
categories: Programming
---

It seems little late to talk about new features in Java 8 at this point of time, it's been already 2 years since it's released and people are talking about Java 9. There are 2 types of Java developers either who are interested and studying 8 but still not using it in production environment or already switched to Scala in response to the necessity of functional programming when I was talking to people in Java related meetups here in Singapore. Due to the late response of changing world, Java 8 seems to be hanging, able to be neither. It's treated like a subject of study for late adapters or an obsolete one for early functional programming adapters.

I also didn't catch up the new features of Java because I didn't use it in my previous company and tried to learn a different language. But I can't avoid it anymore because I still choose it as a primary language when I participate in Coding test.



# Introduction to Lambda
## Introduction to Lambda

Lambda is not very familiar but also not a totally new one for me. When I was coding with C#, I saw a strange mark "=>" and founded and it's called Lambda on the internet (It's used like "->" in Java). But I couldn't understand it and didn't try to figure out very much at that time. Since it became the hottest topic of 8, let's look at it more carefully this time.

First of all, let's define an interface class.

{% highlight java %}
interface Calculator {
    int calculate(int first, int second);
}
{% endhighlight %}

There is a method named calculate, that will do something with input parameters first and second. But action of the method is not implemented because it's an interface. This's called an abstract method, and if there is one abstract method in a interface class, we call it functional interface. Lambda is a way to implement action of this kind of abstract method when this kind of functional interface is called.

Calculator 라는 인터페이스 클래스가 있고, 그 안에 first, second 두 파라메터를 받아 무언가를 수행할 calculate 라는 메소드가 있다. 이 메소드는 구현체가 없는 추상 메소드 이고,  이렇게 단 하나의 추상 메소드가 있는 경우를 함수형 인터페이스라 한다. Lambda 는 이러한 함수형 인터페이스 호출 시 추상 메소드에 코드의 구현체를 넣는 방법이라 할 수 있다.

class Operator {
    public void operate(Calculator calculator){
        int result = calculator.calculate(2,3);
        System.out.println(result);
    }
}
There is a class named Operator. And the method name operate calls calculate in Calculator then print the return value.

Operator 라는 클래스가 있다. 이 Operator는 operate 라는 메소드안에서 Caculator의 caculate 메소드에 입력값을 넣고 그 출력값을 받아와 출력해 준다.

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
Then, execute the operate method in the main method. When the operate method is called, it calls the caculate method, which is an abstract, so the action should be implemented. In previous Java versions under 8, constructs Calculator, and write all words that requires following calculate methods, then I can write action within {}.

이제 main 메소드에서 Operator의 operate 메소드를 실행해 보자. operate 메소드는 Caculator의 calculate 메소드를 호출해야 하는데, 이 메소드는 추상 메소드이므로 메소드가 수행할 내용을 구현해 주어야 한다. 기존 8 미만의 자바 버젼에서는 "//traditional way" 로 주석 처리한 부분과 같이  Calculator 클래스를 생성하고 그 안에 calculate 메소드를 모두 형태에 맞게 적은 다음 {} 안에 수행할 내용을 적었다.

        // traditional way
        operator.operate(new Calculator(){
            public int calculate(int first, int second){
                return first + second;
            }
        });
On the contrary, the code can be much more simplified if I use Lambda expression.

반면, 람다식을 이용한다면 동일한 내용을 아래와 같이 간략하게 표현할 수 있다.

        // using Lambda
        operator.operate( (first, second) -> {
            return first * second;
        });
The existing code only to follow formality, which is  so called boilerplate or ceremony code, is removed such as "new Calculator()" and "public int calculate". And there are only required parameters and actions within {}. The trend of modern programming language is removing this kind of ceremony code due to it hinders productivity and quality of computer programming.

실제 수행 내용과 관계 없이 형식을 맞추기 위해 필요했던 코드 (이를 보일러플레이트 혹은 행사코드라 한다) 들 "new Calculator()", "public int calculate" 이 사라지고,  필요한 파라메터만  적은 후 {} 안에 메소드의 구현체만 적을수 있게 간략해졌다. 이러한 행사코드 들은 프로그래밍에서 생산성과 품질의 향상에 큰 영향을 미치는 것으로 알려져 있으며, 모던 언어들의 공통적인 발전 방향은 이러한 행사코드를 최대한 제거하는 추세이다.

It became a long explanation just with Lambda. Other features will be continued next time...

Java 8의 새로 도입된 내용들을 다 요약하고나 하는 취지였으나, Lambda 주제 하나만으로도 벌써 이렇게 길어져 버렸다. 나머지는 내용은 다음 기회에...
