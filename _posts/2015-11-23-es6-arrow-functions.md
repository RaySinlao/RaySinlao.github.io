---
layout: blog_post
title: ES6 - Arrow Functions
---
 

Things that I learned about the Javascript arrow functions are that they: 

- Create shorter functions 
- Create anonymous functions unless you set them to a var
- Use a 'lexical this' where each function defines it's own 'this' context
<!--- Can't be used as constructor functions where you use the keyword 'new'-->

I'll go over each of these things. In really really light detail. 

<hr>

##Creates Shorter Functions 

You can skip using the parenthesis () and the brackets {}
{% highlight javascript %}

param => console.log(param)

{% endhighlight %}

ES5 translation
{% highlight javascript %}

(function (param) {
  return console.log(param);
});

{% endhighlight %}


<hr>

You could also add more parameters by wrapping the params parenthesis


{% highlight javascript %}

(param1, param2) => console.log(param1, param2)

{% endhighlight %}

ES5 Translation

{% highlight javascript %}

(function (param1, param2) {
  return console.log(param1, param2);
});

{% endhighlight %}

<hr>

In this example I'm wrapping the returned object in parenthesis

{% highlight javascript %}

x => ({name: x, age: 29});

{% endhighlight %}


{% highlight javascript %}

(function (x) {
  return { name: x, age: 29 };
});

{% endhighlight %}

##Creates Anonymous Functions

When I write JS I make heavy usage of declared functions and that was one of the first things that confused me about the arrow functions. If you noticed in the examples above they were all self executing anonymous functions. 

You can create a named function expression by declaring the arrow function as a variable. (There are benefits to using named function expressions https://kangax.github.io/nfe/)

{% highlight javascript %}

var saySomething = param1 => console.log(param1)

{% endhighlight %}

ES5 Translation

{% highlight javascript %}

var saySomething = function saySomething(param1) {
  return console.log(param1);
};

{% endhighlight %}

<hr>


##Lexical This

>Lexical scoping (sometimes known as static scoping ) is a convention used with many programming languages that sets the scope (range of functionality) of a variable so that it may only be called (referenced) from within the block of code in which it is defined.

The arrow function creates a lexical this where this will always refer to the origin function. In this example the Person is aging in increments of 1, every second. If you create a new instance of person and console.log 'p.age' it will return the value of the age depending on how many seconds passed. 

{% highlight javascript %}

function Person(){
  this.age = 0;

  setInterval(() => {
    this.age++; 
  }, 1000);
}

var p = new Person();

console.log(p.age) // after 5 seconds this will say 5

{% endhighlight %}

Without using the arrow function 'this' will refer to the new instance's age. So every time you console.log 'p.age' it will respond with 0 because 'this' is referring to 'p' and not 'Person'. (I definitely have to run this through someone else to know if I am correct)


{% highlight javascript %}

function Person(){
  this.age = 0;

  setInterval(function() {
    this.age++; 
  }, 1000);
}

var p = new Person();

console.log(p.age) // after 5 seconds this will say 0

{% endhighlight %}


