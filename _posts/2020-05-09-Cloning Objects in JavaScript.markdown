---
layout: post
title: "Cloning Objects in JavaScript"
date: 2020-05-09 18:00:00 -0700
tags: [JavaScript, Arrays, Objects, Cloning, Deep Cloning, Shallow Cloning, Deep Copy, Shallow Copy]
comments: true
---

Cloning an object means making a copy of an existing object. 

It is quite straightforward to copy primitive types such as `Number`, `Boolean`, etc. It can be done by just assigning the value to a new variable:

{% highlight javascript %}

var a = 10;
var b = a; // Copies value.

{% endhighlight %}

## The Problem

Things get complicated when dealing with reference types such as `Object`, `Array`, etc. Copying an object by assignment operator doesn't copy its value but copies its reference.

{% highlight javascript %}

var original = ["red", "blue"]; 
var copy = original; // Copies reference.
copy.push("green"); // Adds new item.

console.log(original); // Outputs ["red", blue", "green"]

{% endhighlight %}

When we add an item to the copied array, surprisingly, it gets added to the original array as well. This is because by using assignment operator, we didn't copy the array values but copied the array reference. Here both the variables are pointing to the same location in memory, and therefore modifying one modifies the other. 

So, how can we properly clone an object?

There are several ways to do that which we'll look into below. Also, keep in mind that there are two types of cloning — deep cloning and shallow cloning.

## Deep Cloning

{% highlight javascript %}

var original = ["red", "blue"]; 
var copy = JSON.parse(JSON.stringify(original)); // Creates a deep copy.

{% endhighlight %}

Cloning an object (arrays are objects too) as shown above, creates a deep clone of the original object. This newly minted object is completely independent of the original object.

`JSON.parse(JSON.stringify())` isn't a fancy syntax. We are calling [JSON.stringify()] method first which converts the object to a JSON string. And then we are passing this JSON string to [JSON.parse()] method which converts it to a JavaScript object.

We can write the same in multiple steps as shown below: 

{% highlight javascript %}

var original = ["red", "blue"]; 
var str = JSON.stringify(original); // Converts the object to a JSON string.
var copy = JSON.parse(str); // Converts the JSON string to an object.

{% endhighlight %}

`JSON.parse(JSON.stringify())` performs deep cloning of an object. Deep cloning means that if there are nested objects (objects containing other objects as properties), their values are copied not their references. And this goes on for as many nested levels in the object. This becomes more clear when we look at the example in the next section.

But with `JSON.parse(JSON.stringify())`, there will be data loss if the object has `Date`s, functions, `undefined`, `Infinity`, Maps, Sets, or other complex types. In such case, it is better use any library which supports cloning of objects with these types. For example, Lodash's [cloneDeep()][cloneDeep()] method creates a deep clone of an object. Take a look at the library or framework you are already using, it might have such a function.

## Shallow Cloning

ES6 introduced [Object.assign()][Object.assign()] method and [spread syntax][spread syntax]. Both these can be used to perform shallow cloning of an object. Shallow cloning means that if there are nested objects, their references are copied not their values.

This can be sufficient when not dealing with nested objects, as in the example below.

{% highlight javascript %}

var original = ["red", "blue"]; 
var copy1 = Object.assign({}, original); // Using Object.assign() method.
var copy2 = [...original]; // Using spread syntax.

{% endhighlight %}

But when cloning an object with nested objects, it is required to create a deep clone of an object to avoid any unintended effects.

Let's look at an example.

{% highlight javascript %}

var person = { 
  "name": "Nikhil", 
  "favorites": {
    "color": "blue",
    "game": "chess"
  }
};

var copy = { ...person }; // Creates a shallow copy.
copy.name = "Sachin";
copy.favorites.game = "cricket"; // Also modifies the original 'person' object.

console.log(person);
// Outputs { name: "Nikhil", favorites: { color: "blue", game: "cricket" } }

{% endhighlight %}

As we can see in the above example, modifying the `copy` object's `favorites` property also modified the original `person` object's `favorites` property. This is because we created a shallow copy of the original object, not a deep copy.  

If we instead create a deep copy as shown below, then modifying the copied object doesn't affect the original object. The copied object is completely independent of the original object.

{% highlight javascript %}

// Deep cloning.
var copy = JSON.parse(JSON.stringify(person)); 

{% endhighlight %}


[JSON.stringify()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify
{:target="_blank"}
[JSON.parse()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse
{:target="_blank"}
[cloneDeep()]: https://lodash.com/docs#cloneDeep
{:target="_blank"}
[Object.assign()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign
{:target="_blank"}
[spread syntax]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax
{:target="_blank"}
