---
title: "How I solved Scotch.io Code Challenge #11: Javascript Functional Programming "
date: "2019-02-04T10:40:32.169Z"
layout: post
draft: false
path: "/posts/functional_programming_scotchio/"
category: "Javascript"
tags:
 - "Functional programming"
 - "ES6"
 - "Javascript"
description: "My solution to this fun challenge using mostly map, reduce and filter"
---

Scotch.io code challenges are awesome. I just discovered them last week and immediately dove into the functional programming one since its what I've been learning lately. The challenge consisted basically on manipulating arrays using any of the following methods:

- .map()
- .filter()
- .find()
- .replace()
- .reduce()
- forEach()

## Section 1

On the first section, the following array was provided:

```js
const texas = [
 {
  name: "Mike",
  age: 23,
  gender: "m",
  us: false
 },
 {
  name: "Liz",
  age: 22,
  gender: "f",
  us: true
 },
 {
  name: "Chris",
  age: 102,
  gender: "m",
  us: true
 },
 {
  name: "Chuloo",
  age: 27,
  gender: "m",
  us: false
 },
 {
  name: "Annie",
  age: 30,
  gender: "f",
  us: true
 }
];
```

### The Challenge

1. **Find all users older than 24**

This I did using the .filter() method. This method creates a new array with all the elements that pass the test. In this case, the method iterates over all objects in the array filtering the ones whose age property value is greater than 24.

```js
const older24Texas = texas
.filter(item => item.age > 24);
console.log(older24Texas);
/* 
[Object {
  name: "Chris",
  age: 102,
  gender: "m",
  us: true
 },
 Object {
  name: "Chuloo",
  age: 27,
  gender: "m",
  us: false
 },
 Object {
  name: "Annie",
  age: 30,
  gender: "f",
  us: true
 }
];
*/
```

2. **Find the total age of all users**

The .reduce() method is great for sums or products. This method executes a reducer function (that you provide) on each member of the array resulting in a single output value. The reducer function provided in this case is just a function that adds the accumulator and the current value on each iteration.

```js
const totalAgeTexas = texas
.map(i => i.age)
.reduce((acc, curr) => acc + curr);
console.log(totalAgeTexas); /* 204 */
```

3. **List all female coders**

For this one, I used the .filter() method again to create a new array containing females only. After it, I used a .map() method , which creates a new array with the results of calling a provided function on every element in the calling array. In this case, the function inside the map method only returns the values of the name property of each object.

```js
const femaleTexas = texas
.filter(i => i.gender === "f")
.map(i => i.name);
console.log(femaleTexas); /* ["Liz", "Annie"] */
```

## Section 2

A new array was provided :

```js
const newyork = [
 {
  name: "Michelle",
  age: 19,
  coder: true,
  gender: "f",
  us: true
 },
 {
  name: "Sam",
  age: 25,
  coder: false,
  gender: "m",
  us: false
 },
 {
  name: "Ivy",
  age: 26,
  coder: true,
  gender: "f",
  us: false
 },
 {
  name: "Nick",
  age: 32,
  coder: true,
  gender: "m",
  us: true
 },
 {
  name: "Jim Beglin",
  age: 65,
  coder: false,
  gender: "m",
  us: true
 }
];
```

### The Challenge

1. **List all users in US in ascending order**

Similarly to the first section challenge, I first filtered the array of objects with the people from US. Then created an array (using .map()) and sorted it using the .sort() method.

```js
const allUSNewyork = newyork
 .filter(i => i.us)
 .map(i => i.name)
 .sort();
console.log(allUSNewyork); /* ["Jim Beglin", "Michelle", "Nick"] */
```

2. **Sort all users by age**

This one was interesting because I had to make a tweek on the sort function. Instead of just calling the method, I passed it a function specifying what values I want it to sort. For this one I tweeked some values of the ages of the people just to test it out.

```js
const sortedNewYork = newyork.sort((a, b) => a.age - b.age);
console.log(sortedNewYork);
/*
[
  {
  name: "Nick",
  age: 3,
  coder: true,
  gender: "m",
  us: true
 },
 {
  name: "Michelle",
  age: 19,
  coder: true,
  gender: "f",
  us: true
 },
 {
  name: "Ivy",
  age: 26,
  coder: true,
  gender: "f",
  us: false
 },
 {
  name: "Sam",
  age: 28,
  coder: false,
  gender: "m",
  us: false
 },
 {
  name: "Jim Beglin",
  age: 65,
  coder: false,
  gender: "m",
  us: true
 }
];
*/
```

3. **List all female coders**

This one was exactly like the one on the previous section.

```js
const femaleNewYork = newyork
.filter(i => i.gender === "f")
.map(i => i.name);
console.log(femaleNewYork); /* ["Michelle", "Ivy"] */
```

## Section 3

The last array provided:

```js
const vegzas = [
 {
  name: "Charly",
  age: 32,
  coder: true,
  gender: "m"
 },
 {
  name: "Law",
  age: 21,
  coder: true,
  gender: "m"
 },
 {
  name: "Rosey",
  age: 42,
  coder: false,
  gender: "f"
 },
 {
  name: "Steph",
  age: 18,
  coder: true,
  gender: "f"
 },
 {
  name: "Jon",
  age: 47,
  coder: false,
  gender: "m"
 }
];
```

### The Challenge

1. **Find the total age of male coders under 25**

On this one I finally got to use the three methods together, first filtered, then map to be able to reduce it to the sum of all male coders under 25.

```js
const totalunder25Vegzas = vegzas
 .filter(i => i.age < 25)
 .map(i => i.age)
 .reduce((a, b) => a + b);
console.log(totalunder25Vegzas); /* 39 */
```

2. **List all male coders over 30**

used a double filter in order to l

```js
const allmaleover30Vegzas = vegzas
 .filter(i => i.gender === "m")
 .filter(i => i.age > 30)
 .map(i => i.name);
console.log(allmaleover30Vegzas); /*["Charly", "Jon"]*/
```

3. **Find the total age of everyone in texas, newyork and vegzas combined.**

This last challenge was a bit different because it involved all three arrays. In this case, I used the spread operator to concatenate all arrays, then map to get the ages, and finally reduced it to the sum of all the ages. More on th spread operator on the newx blog post!

```js
const totalArrays = [...vegzas, ...newyork, ...texas]
 .map(i => i.age)
 .reduce((a, b) => a + b);
console.log(totalArrays); /* 529 */
```

Thanks for reading. Check out the challenge at [Scotch.io](https://scotch.io/bar-talk/code-challenge-11-javascript-functional-programming) and try it yourself!
