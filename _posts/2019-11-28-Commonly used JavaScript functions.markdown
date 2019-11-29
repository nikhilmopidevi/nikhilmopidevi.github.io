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
