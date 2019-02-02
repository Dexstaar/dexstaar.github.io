

# Promise 
Promise
   => Resolved => then
   => rejected => catch

{% highlight javascript %}
let promise = new Promise((resolve, reject) => {
    resolve();
    //reject();
});

promise
    .then(() => console.log('finally finished!'))
    .then(() => console.log('i was also ran!!!'))
    .catch(() => console.log('uh oh!!'));
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
{% highlight javascript %}
function printlog() {
    return new Promise(resolve => {
        setTimeout(() => {
        resolve('resolved');
        }, 2000);
    });
}

async function asyncCall() {
  console.log('before');
  var result = await printlog();
  console.log(result);
  console.log('after');
}

asyncCall();

{% endhighlight %}