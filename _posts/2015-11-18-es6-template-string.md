---
layout: blog_post
title: ES6 - Template Strings
---

Template strings make your code a lot more manageable when creating strings that have changing variables. 

##Oldschool

{% highlight javascript %}

var name = "Ray";
var text = "Hello, my name is " + name + ". Welcome to my blog!"

console.log(text); // Hello, my name is Ray. Welcome to my blog!

{% endhighlight %}


##Newschool

Using the ${} will add the variable to the string. You don't have to create any breaks and your code turns out a lot cleaner.

{% highlight javascript %}

var name = "Ray";
var text = "Hello, my name is ${name}. Welcome to my blog!"

console.log(text); // Hello, my name is Ray. Welcome to my blog!

{% endhighlight %}