---
layout: blog_post
title: ES6 - Destructuring
---

Destructuring is really interesting. It will allow you to extract only the values that you need and assign it to a variable.

A really simple example would be extracting data from an object: 

{% highlight javascript %}

var data = [
  {
    name: 'A$AP Rocky',
    description: {
      origin: 'Brooklyn',
      genre: 'Rap'
    }
  }
];


// Destructuring
var {name, description:{origin, genre}} = data[0];

console.log(name);   // A$AP Rocky
console.log(origin); // Brooklyn
console.log(genre);  // Rap


// Without destructuring
console.log(data.name);                // A$AP Rocky
console.log(data.description.origin);  // Brooklyn
console.log(data.description.genre);   // Rap
{% endhighlight %}

It can cut down on a lot of confusion and errors when you remove the whole selecting data through chaining properties. 

<br>

###Destructuring Arrays

You can break out your arrays and assign each value to it's own property:

{% highlight javascript %}

var numbers = [1, 2, 3];

// Destructuring
var [one, two, three] = numbers; 
console.log(one, three);     // one three

// What destructuring is basically doing
var one   = numbers[0];
var two   = numbers[1];
var three = numbers[2];
{% endhighlight %}

If you don't feel like extracting every value to an array you can skip positions in the array.

{% highlight javascript %}

var numbers = [1, 2, 3];

var [,,three] = numbers;

console.log(three); // 3
{% endhighlight %}

<br>


###Destructuring Objects

The first A$AP Rocky example was basically destructuring an object but there is another way to change the key if you need. 

This example will extract the rapper's name and reassign it to it's own variable:

{% highlight javascript %}

var rapper1 = {name: 'Biggie'};
var rapper2 = {name: 'Tupac'};

var {name: name1} = rapper1;
var {name: name2} = rapper2;

console.log(name1); // Biggie
console.log(name2); // Tupac
{% endhighlight %}






