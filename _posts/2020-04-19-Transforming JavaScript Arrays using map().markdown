---
layout: post
title: "Transforming JavaScript Arrays using map()"
date: 2020-04-19 22:00:00 -0700
tags: [JavaScript, Arrays, Objects]
comments: true
---

[Array.prototype.map()][Array.prototype.map()] method creates and returns a new array with the results of calling a provided function on every element in the calling array.

We can use this method to transform or change elements of an array.

In the following example, we add number `10` to every number in the initial array `nums`. The resultant array returned by `map()` is stored in the variable `newNums`. The original array isn't modified.

## Example

{% highlight javascript %}

const nums = [2, 4, 6, 8];

const newNums = nums.map(num => num + 10);

for (let num of newNums) {
  console.log(num);
}

{% endhighlight %}

## Output

{% highlight javascript %}

12
14
16
18

{% endhighlight %}

Let us look at another example of using `map()` on an array containing objects.

## Example

{% highlight javascript %}

const productsInUSD = [
  { "item": "pen", "price": "2" },
  { "item": "pencil", "price": "1" },
  { "item": "notebook", "price": "3" }
];

const productsInINR = productsInUSD.map(product => {
  return {
    "item": product.item,
    "price": product.price * 75
  };
});

for (let product of productsInINR) {
  console.log(`${product.item} - Rs.${product.price}`);
}

{% endhighlight %}

## Output

{% highlight javascript %}

pen - Rs.150
pencil - Rs.75
notebook - Rs.225

{% endhighlight %}

We can also use latest ES6 features and write the `map()` method as:

{% highlight javascript %}

const productsInINR = productsInUSD.map(product => ({
  ...product,
  "price": product.price * 75
}));

{% endhighlight %}

## Avoid mutating original array
 
When using `map()` on an array of objects, be careful to avoid mutating (modifying) original array and make sure to return a new object from the callback function.

{% highlight javascript %}

// Don't do this.
const productsInINR = productsInUSD.map(product => {
  let newProduct = product;
  newProduct.price = product.price * 75;
  return newProduct;
});

{% endhighlight %}

At first glance, the above code looks good. But we should observe that we are assigning an object reference to `newProduct`, therefore modifying `newProduct` also modifies the original object.

If we print `productsInUSD` array elements to the console, we can see that they are modified and now contain prices in INR. This isn't desired and breaks functionality in other parts of our application.

To avoid this, clone the object before assigning. There are [several ways to clone an object]({{ site.baseurl }}{% post_url 2020-05-09-Cloning Objects in JavaScript %}){:target="_blank"}, let us use `JSON.parse(JSON.stringify(object))` for this example.

{% highlight javascript %}

const productsInINR = productsInUSD.map(product => {
  let newProduct = JSON.parse(JSON.stringify(product));
  newProduct.price = product.price * 75;
  return newProduct;
});

{% endhighlight %}

This doesn't modify the original array and prevents any unintended effects.


[Array.prototype.map()]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
{:target="_blank"}
