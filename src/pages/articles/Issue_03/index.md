---
title: Awesome things that can be done with Array.from()
date: '2019-01-27T08:40:32.169Z'
layout: post
draft: true
path: '/posts/array_from/'
category: 'Javascript'
tags:
  - 'Methods'
  - 'ES6'
  - 'Javascript'
description: "Array.from() is an awesome method introduced with ES6. This post includes practical examples of how I use it."
---

Array.from() is  great method to have in your bag of tricks. According to the MDN definition, it is a method that "creates a new shallow-copied instance from an array like or iterable object". 

### Examples

If you have an HTML Collection or Nodelist, which are array-like objects, you don't have access to the methods from the Array.prototype. In order to be able to access them, you can use Array.from() method an have these Collections or Nodelists in array form.

```html
 <ul>
    <li class="item">Item 1</li>
    <li class="item">Item 2</li>
    <li class="item">Item 3</li>
    <li class="item">Item 4</li>
    <li class="item">Item 5</li>
  </ul>
```
```js
const lis = document.getElementsByTagName("li"); /*lis is here an HTML collection*/

const arr = Array.from(lis); /*It is now an array*/

```

You can also create an array from another type of array-like object: arguments.

```js
function foo() {
  console.log(Array.from(arguments));
}

foo( 1, "firstName", true); /*[1, "firstName", true] */

```
Sometimes you need a string converted into an array, and this method can do it for you too as an alternative to the String.split method

```js

console.log(Array.from("Nelson")); /*["N","e","l","s","o","n"]*/

```

### The optional parameter : the map function

In my previous post, I used Array.from() to create an array of consecutive numbers. 

```js
console.log(Array.from({ length: 5 }, (item, index) => index)); /* [0, 1, 2, 3, 4] */
```
This is possible because the Array.from() takes an array-like object or iterable object as a first parameter but also an optional second parameter which is a map function. 

In this case, the iterable object is of length 5, and the map function returns the current index of each item, generating a sequence of numbers.

Without the map function, the method would still return an array from the object, but it would just have undefined set to each of the 5 values:

```js
console.log(Array.from({ length: 5 })); /* [undefined, undefined, undefined, undefined, undefined] */
```


Hope you found this on useful!



