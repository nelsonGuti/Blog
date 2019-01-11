---
title: Reverse a String using Javascript
date: "2019-01-25T22:40:32.169Z"
layout: post
draft: false
path: "/posts/reverse-a*string/"
category: "Javascript"
tags:
  - "FreeCodeCamp"
  - "Algorithm"
  - "Javascript"
description: "FreeCodeCamp's basic algorithm scripting section helped me a lot to improve my JS skills. This post covers my solution to the 'Reverse a String Challenge'."
---

FreeCodeCamp's basic algorithm scripting section is a great resource to start testing if you are grasping all the Vanilla JS concepts. I will be blogging about my solutions to these challenges. They might not be the best, but I hope I can share what my thought process was behind each function I wrote.

This time will be covering the Reverse a String Challenge. Like all the other challenges, it consists of basically writing a javascript function. The instructions usually provide a hint or two on how to solve the problem. This challenge provided the following information:

1. Reverse the provided string
2. You may need to turn the string into an array before you can reverse it.
3. Your result must be a string

The first hint is to convert the string into an array. Why would this be? Hang with me, we will understand it in a bit. I decided to use the String.prototype.split() method I learned in the previous FCC lessons to achieve this. This method basically 'splits' the string into an array of strings. After using this method, my function looked like this:

```js
function reverseString(str) {

      const arr = st.split("").

      return arr; 
  
}

reverseString("Nelson"); /* ["N", "e", "l", "s", "o", "n"] */


```

Now, we have a function that takes a string and returns an array of all the letters of the string. Having our information as an array, we have now have access to all the Array.prototype methods javascript provides us. One of them is Array.prototype.reverse(). The String.prototype does not have its own reverse method, so this is why converting the string to an array was a great hint. After using the reverse method, my function looked like this:

```js
function reverseString(str) {

      const arr = st.split("").

      return arr.reverse(); 
  
}

reverseString("Nelson"); /* ["n", "o", "s", "l", "e", "N"] */
```

Having the information already reversed, the last step I had to do was to convert it back to a string. To do this I used the Array.prototype.join() method, which returns a new string by concatenating or joining all the elements in the array. My function then looked like this:

```js
function reverseString(str) {

  const arr = str.split("");
  const arrReversed = arr.reverse();
  const newString = arrReversed.join("");
  
  return newString;
}

console.log(reverseString("nelson")); /* noslen */
```

This finally unlocked the challenge and I had a working function that did exactly what the instructions said it should. Nonetheless, I realized the code could be greatly reduced in size by writing all the methods in a single line. This was my final result.

```js
function reverseString(str) {
 
  return str.split("").reverse().join("");
}

console.log(reverseString("nelson")); /* noslen */
```

