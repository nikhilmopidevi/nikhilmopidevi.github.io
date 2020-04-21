---
layout: post
title: "Iterating over Object properties in JavaScript"
date: 2020-04-13 20:00:00 -0700
tags: [JavaScript, Objects]
comments: true
---

There are several ways to iterate over an object's properties in JavaScript.

[Object.entries()][Object.entries()] returns an array of object's own enumerable string-keyed property `[key, value]` pairs. This array can then be iterated over using [forEach()][Array.prototype.forEach()] or [for...of][for...of].

## Example

{% highlight javascript %}

const book = {
  "title": "The Fountainhead",
  "author": "Ayn Rand",
  "pages": 753
};

Object.entries(book).forEach(([key, value]) => {
  console.log(`${key}: ${value}`);
});

{% endhighlight %}

## Output

{% highlight javascript %}

title: The Fountainhead
author: Ayn Rand
pages: 753

{% endhighlight %}

Similarly, `for...of` can also be used with `Object.entries()`.

{% highlight javascript %}

for (let [key, value] of Object.entries(book)) {
  console.log(`${key}: ${value}`);
}

{% endhighlight %}

## for...in

`for...in` statement can also be used to iterate over object properties, but it also iterates over inherited properties. Luckily, [hasOwnProperty()][hasOwnProperty()] method can be used to check if a property is object's own property.

{% highlight javascript %}

const book = {
  "title": "The Fountainhead",
  "author": "Ayn Rand",
  "pages": 753
};

for (let key in book) {
  if (book.hasOwnProperty(key)) {
    console.log(`${key}: ${book[key]}`);
  }
}

{% endhighlight %}

## Object.keys() and Object.values()

If we are only concerned with object property keys, then `Object.keys()` can be used. Similarly, `Object.values()` can be used to get object property values.

{% highlight javascript %}

const book = {
  "title": "The Fountainhead",
  "author": "Ayn Rand",
  "pages": 753
};

Object.keys(book).forEach(key => {
  console.log(key);
});

Object.values(book).forEach(value => {
  console.log(value);
});

{% endhighlight %}


[Object.entries()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries
{:target="_blank"}
[Array.prototype.forEach()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach 
{:target="_blank"}
[for...of]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of 
{:target="_blank"}
[hasOwnProperty()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty
{:target="_blank"}