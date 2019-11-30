---
layout: post
title: "Commonly used JavaScript String, Array, and Object methods"
date: 2019-11-28 10:00:00 +0530
tags: [JavaScript, functions, methods]
comments: true
---

## Introduction

In this post, we will look at some commonly used JavaScript String, Array, and Object methods and some insights on choosing the right method based on the task.

Clicking on a method name opens a new tab with its MDN documentation. You can refer it for more information and usage examples.

## String methods
Following are some of the common methods from the [String][String] global object.

- [indexOf()][String.prototype.indexOf()] - This method returns the index of the passed string within the string. Returns -1 if the value is not found.
- [includes()][String.prototype.includes()] - This method returns _true_ or _false_ based on whether the passed string exists within the string.

Use `indexOf()` if you need the position of the passed string in the string. Use `includes()` if you are only concerned whether the passed string exists, it makes intent of the code more clear.

- [trim()][String.prototype.trim()] - This method removes whitespace from both ends of a string.
- [split()][String.prototype.split()] - This method returns an array of strings by separating the string at each instance of a specified separator string.
- [substring()][String.prototype.substring()] - This method returns the part of the string between the start and end indexes.
- [slice()][String.prototype.slice()] - This method is quite similar to `substring()` with some [differences][StackOverflow - slice() vs substring()].

## Array methods
Following are some of the common methods from the [Array][Array] global object.

- [forEach()][Array.prototype.forEach()] - This method executes a provided function once for each array element.
- [indexOf()][Array.prototype.indexOf()] - This method returns the first index at which a given element can be found in the array, or -1 if it is not present.
- [includes()][Array.prototype.includes()] - This method returns _true_ or _false_ based on whether the passed value is contained in the array.

Just like with `String` methods, use `indexOf()` if you need the position of the value in the array. Use `includes()` if you are only concerned whether the value exists, it makes intent of the code more clear.

`indexOf()` and `includes()` use [strict equality][Strict equality] (the same method used by the === or triple-equals operator) for comparing the search element with the elements of the Array. So, when used on an array containing objects, object references are compared not the actual values.

Therefore, when dealing with array of objects, use `some()`, `find()`, or `findIndex()` methods.

- [find()][Array.prototype.find()] - This method returns the value of the first element in the array that satisfies the provided testing function. Otherwise, `undefined` is returned.
- [findIndex()][Array.prototype.findIndex()] - This method returns the index of the first element in the array that satisfies the provided testing function. Otherwise, it returns -1.
- [some()][Array.prototype.some()] - This method tests whether **at least one element** in the array passes the test implemented by the provided function. It returns _true_ or _false_ appropriately.
- [every()][Array.prototype.every()] - This method tests whether **all elements** in the array passes the test implemented by the provided function. It returns _true_ or _false_ appropriately.

Following methods are used for filtering and transforming an array.

- [filter()][Array.prototype.filter()] - This method creates and returns a new array with all elements that pass the test implemented by the provided function.
- [map()][Array.prototype.map()] - This method creates and returns a new array with the results of calling a provided function on every element in the calling array.
- [reduce()][Array.prototype.reduce()] - This method executes a provided reducer function on each element of the array, resulting in a single output value. This final output value is returned.
- [splice()][Array.prototype.splice()] - This method modifies the contents of the array by adding or removing new elements in-place.
- [join()][Array.prototype.join()] - This method is the opposite of [String.prototype.split()][String.prototype.split()]. It creates and returns a new string by concatenating all array elements, separating them by a specified separator string.

## Object methods
Following are some of the common methods from the [Object][Object] global object.

- [keys()][Object.keys()] - This method returns an array of a given object's own enumerable property names, in the same order as we get with a normal loop.
- [values()][Object.values()] - This method returns an array of a given object's own enumerable property values, in the same order as that provided by a [for...in][for...in] loop.
- [entries()][Object.entries()] - This method returns an array of a given object's own enumerable string-keyed property `[key, value]` pairs, in the same order as that provided by a [for...in][for...in] loop.
- [fromEntries()][Object.fromEntries()] - This method is the opposite of `Object.entries()`. It transforms a list of key-value pairs into an object.

One of the best ways to learn more these methods is to click on their links, read the documentation, and play around with some examples.

[String]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String 
{:target="_blank"}
[String.prototype.indexOf()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf 
{:target="_blank"}
[String.prototype.includes()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes 
{:target="_blank"}
[String.prototype.trim()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trim 
{:target="_blank"}
[String.prototype.split()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split 
{:target="_blank"}
[String.prototype.substring()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring 
{:target="_blank"}
[String.prototype.slice()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice 
{:target="_blank"}
[StackOverflow - slice() vs substring()]: https://stackoverflow.com/a/2243835/2924577

[Array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array
{:target="_blank"}
[Array.prototype.forEach()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach 
{:target="_blank"}
[Array.prototype.indexOf()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf 
{:target="_blank"}
[Array.prototype.includes()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes 
{:target="_blank"}
[Strict equality]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Identity 
{:target="_blank"}
[Array.prototype.find()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find 
{:target="_blank"}
[Array.prototype.findIndex()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex
{:target="_blank"}
[Array.prototype.some()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some 
{:target="_blank"}
[Array.prototype.every()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every 
{:target="_blank"}
[Array.prototype.filter()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter 
{:target="_blank"}
[Array.prototype.map()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map 
{:target="_blank"}
[Array.prototype.reduce()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce 
{:target="_blank"}
[Array.prototype.splice()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice 
{:target="_blank"}
[Array.prototype.join()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join 
{:target="_blank"}

[Object]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object
{:target="_blank"}
[Object.keys()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys
{:target="_blank"}
[Object.values()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values
{:target="_blank"}
[for...in]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in
{:target="_blank"}
[Object.entries()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries
{:target="_blank"}
[Object.fromEntries()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/fromEntries
{:target="_blank"}
