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


var math = "10 Plus 10 is " + (10 + 10) + " and not " + (10 - 10);

console.log(math); // 10 Plus 10 is 20 and not 0

{% endhighlight %}


##Newschool

Using the ${} will add the variable to the string or handle math equations. Also, those are backticks and not quotation marks.

{% highlight javascript %}

var name = "Ray";
var text = `Hello, my name is ${name}. Welcome to my blog!`

console.log(text); // Hello, my name is Ray. Welcome to my blog!


var math = `10 Plus 10 is ${ 10 + 10 } and not ${ 10 - 10 }`;

console.log(math); // 10 Plus 10 is 20 and not 0

{% endhighlight %}