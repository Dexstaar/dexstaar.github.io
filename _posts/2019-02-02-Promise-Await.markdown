---
layout: post
title:  "Promise and Async/Await"
date:   2019-02-02 19:55:16 +0800
categories: JavaScript
---



# Promise 
Promise <br/>
   => Resolved => then <br/>
   => rejected => catch <br/>

{% highlight javascript %}
let promise = new Promise((resolve, reject) => {
    if(condition) {
        resolve();
    } else {
        reject();
    }
});

promise
    .then(() => console.log('finally finished!'))
    .then(() => console.log('i was also ran!!!'))
    .catch(() => console.log('uh oh!!'));
{% endhighlight %}


{% highlight javascript %}
function getData() {
  return new Promise(function (resolve, reject) {
    $.get('url/products/1', function (response) {
      if (response) {
        resolve(response);
      }
      reject(new Error("Request is failed"));
    });
  });
}

// Fulfilled or Rejected
getData().then(function (data) {
  console.log(data); // response 
}).catch(function (err) {
  console.error(err); // Error 
});
{% endhighlight %}


# Examples of Promise
Ajax Request with Fetch

{% highlight javascript %}
let url = 'https://jsonplaceholder.typicode.com/posts';

fetch(url)
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.log('BAD', error));
{% endhighlight %}


# Async / Await
Await function should return Pormise.

{% highlight javascript %}
function resolveAfter2Seconds() {
    return new Promise(resolve => {
        setTimeout(() => {
        resolve('resolved');
        }, 2000);
    });
}

async function asyncCall() {
  console.log('before await');
  var result = await resolveAfter2Seconds();
  console.log(result);
  console.log('after await');
}

asyncCall();

{% endhighlight %}