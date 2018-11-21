---
layout: post
title:  "Array helpers in JavaScript"
date:   2018-11-01 00:00:01 +0800
categories: Programming
---


There are array helper methods that help us handle array data structure from ES6 in JavaScript.

# foreach

{% highlight javascript %}
var colors = ['red', 'blue', 'green' ];

for (var i=0; i<colors.length; i++) {
  console.log(colors[i]);
}

colors.forEach(color => {
  console.log(color);
});
{% endhighlight %}




# map
{% highlight javascript %}
var numbers = [1,2,3];
var doubledNumbers = [];

for (var i=0; i<numbers.length; i++) {
  doubledNumbers.push(numbers[i] * 2);
}

var doubled = numbers.map(function(number) {
  return number * 2;
});

doubled;
doubledNumbers;
{% endhighlight %}

{% highlight javascript %}
var cars = [
  { model: 'Buick', price: 'CHEAP' },
  { model: 'Camaro', price: 'expensive' }
];

var prices = cars.map(function(car) {
  return car.price;
});

prices;
{% endhighlight %}



# filter

{% highlight javascript %}
var products = [
  { name: 'cucumber', type: 'vegetable' },
  { name: 'banana', type: 'fruit' },
  { name: 'celery', type: 'vegetable' },
  { name: 'orange', type: 'fruit' }
];

var filteredProducts = [];

for (var i=0; i<products.length; i++) {
  if (products[i].type === 'fruit') {
    filteredProducts.push(products[i]);
  }
}

filteredProducts;

var filteredProducts2 = products.filter(product => {
  return product.type === 'fruit';
});

filteredProducts2;
{% endhighlight %}


{% highlight javascript %}
var products = [
  { name: 'cucumber', type: 'vegetable', quantity: 0, price: 1 },
  { name: 'banana', type: 'fruit', quantity: 10, price: 15 },
  { name: 'celery', type: 'vegetable', quantity: 30, price: 9 },
  { name: 'orange', type: 'fruit', quantity: 3, price: 5 }
];

// Type is 'vegetable', quantity is greater than 0, price is less than 10
products.filter(product => {
  return product.type === 'vegetable'
  	&& product.quantity > 0
  	&& product.price < 10;
});
{% endhighlight %}



{% highlight javascript %}
var post = { id: 4, title: 'New Post' };
var comments = [
  { postId: 4, content: 'awesome post' },
  { postId: 3, content: 'it was ok' },
  { postId: 4, content: 'neat' }
];

function commentsForPost(post, comments) {
  return comments.filter(function(comment) {
    return comment.postId === post.id;
  });
}

commentsForPost(post, comments);
{% endhighlight %}



# find
{% highlight javascript %}
var users = [
  { name: 'Jill' },
  { name: 'Alex' },
  { name: 'Bill' }
];
var user;

for (var i=0; i<users.length; i++) {
  if (users[i].name === 'Alex') {
    user = users[i];
    break;
  }
}

users.find(user => {
  return user.name === 'Alex';
});
{% endhighlight %}


{% highlight javascript %}
var posts = [
  { id: 1, title: 'New Post'},
  { id: 2, title: 'Old Post' }
];

var comment = { postId: 1, content: 'Great Post' };

function postForComment(posts, comment) {
  return posts.find(function(post) {
    return post.id === comment.postId;
  });
}

postForComment(posts, comment);
{% endhighlight %}


# every / some

{% highlight javascript %}
var computers = [
  {name: 'Apple', ram: 24},
  {name: 'Compaq', ram: 4},
  {name: 'Acer', ram: 32}
];

var allComputersCanRunProgram = true;
var onlySomeComputersCanRunProgram = false;

for (var i=0; i<computers.length; i++) {
  var computer = computers[i];
  
  if(computer.ram < 16) {
    allComputersCanRunProgram = false;
  } else {
    onlySomeComputersCanRunProgram = true;
  }
}

computers.every(computer => {
  return computer.ram > 16;
});

computers.some(computer => {
  return computer.ram > 16;
});
{% endhighlight %}



{% highlight javascript %}
var names = [
  'Alexandria',
  'Matthew',
  'Joe'
];

names.every(function(name) {
  return name.length > 4;
});

names.some(function(name) {
  return name.length > 4;
});
{% endhighlight %}






# reduce
