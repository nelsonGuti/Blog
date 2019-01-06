---
title: Factorialize a Number  using Javascript
date: "2018-12-09T22:40:32.169Z"
layout: post
draft: true
path: "/posts/Factorializa-a-Number/"
category: "Javascript"
tags:
  - "FreeCodeCamp"
  - "Algorithm"
  - "Javascript"
description: "My solution to FreeCodecamp's 'Factorialize a Number Challenge', on the Basic Algorithm scripting section. For this one, I used the Array.from and reduce methods"
---

My high school math teacher said factorials was something every one should know and that it would come handy one day. Even though I've never used it in real life, I was excited to at least know what it was when I saw the challenge. The factorial of a number, lets say 'n', is basically the product of all positive integers less than or equal to n. For example: 5! = 1 * 2 * 3 * 4 * 5 = 120

In order to complete the challenge, I decided that the first thing my function would do was to create an array with the numbers from 1 to whatever the input was. Originally, I achieved this using a for loop which looked like this:

```js
function factorialize(num){

	const arr = [];

	for(let i=1;i<=num;i++){
		arr.push(i);
	}

	console.log(arr); /* [1, 2, 3, 4, 5, 6, 7, 8] */
}

factorialize("8"); 

```

Having all the numbers in an array, I knew I could used the reduce method. As it is defined in the MDN documentation page, "the reduce() method executes a reducer function (that you provide) on each member of the array resulting in a single output value." This is incredibly handy because it basically allows you to take a set of numbers, do something with them, and output one single accumulated value. I had used the reduce method for a sum of all the elements in an array in other projects, so I just went ahead and used it similarly but in this case, to multiply all the elements in the array and return the product. At this point my function looked like this:


```js
function factorialize(num){

	const arr = [];

	for(let i=1;i<=num;i++){
		arr.push(i);
	}

	console.log(arr); /* [1, 2, 3, 4, 5, 6, 7, 8] */

	return arr.reduce((a,b)=>a*b); 
}

factorialize(8);/* 40320 */

```
At this point, the challenge was 85% completed. The only issue was that if the function received the number 0, the function wouln't work because it would not enter the for loop, and hence, there would be nothing to iterate over in the reduce, causing an error. So, I decided to fix this using an if statement. 

```js
function factorialize(num){

	if(num === 0){
		return 1;
	}
	else {
		const arr = [];

		for(let i=1;i<=num;i++){
		arr.push(i);
		}

		console.log(arr); 

		return arr.reduce((a,b)=>a*b); 
	}
}

factorialize(0); /* 1 */




```
