---
title: "push(), pop(), shift(), and unshift()"
path: "/array_manipulation"
date: "2020-06-19"
coverImage: ""
author: "Boahs"
excerpt: '"When working with arrays, it is easy to manlipulate them!"'
tags: ["js", "arrays", "fundamentals", "learning", "methods"]
---
# ['Manlipulate','your','arrays']

## .push()

One of the first methods you'll start to use, and see a lot when working with arrays is the .push(); method. This will append any value to the <i>end</i> of an array. 

```javascript
let arr = ['Cats','Dogs','Deer','Lemurs'];
console.log(arr)
//expected output: (4) ["Cats", "Dogs", "Deer", "Lemurs"]
arr.push('Monkies');
console.log(arr)
//expected output: (5) ["Cats", "Dogs", "Deer", "Lemurs", "Monkies"]
```
Not too difficult, right? Let's take it step by step, and see how everything is working exactly inside the code above. 

```javascript
let arr = ['Cats','Dogs','Deer','Lemurs'];
```
We're defining an array with four strings.  An array is a special variable which is able to hold more than one value at the same time. 


```javascript
console.log(arr)
```
We're asking the console to log our defined array.

```javascript
//expected output: (4) ["Cats", "Dogs", "Deer", "Lemurs"]
```
An array unless specified otherwise will always start an index 0 but with the .push() method we're using relies on the .length(); property to determine where to start. This is why the output is (4) - If we were using dot notation to change the array like this : 

```javascript
arr[0] = 'Lions';
```
Then you'll notice 'Cats' will now be replayed with 'Lions'.

```javascript
arr.push('Monkies');
```
Like the example before w/ dot notation instead of manlipulating a value we already have we're PUSHING it all the way to the end of the array. 

## .pop();

```javascript
let arr = [1, 4, 6];
console.log(arr);
//expected output: (3) [1, 9, 4]
arr.pop();
console.log(arr);
//expected output: (2) [1, 9]
```
The pop() method will remove the last element of an array, and return that element. This method will change the length of your array. If you call pop(); on an empty array, it should return undefined. You'll see in the next example the .shift() and .pop() methods have similar behavior. 

```javascript
let arr = ['Boahs', 'Bob', 'Torbjorn']
console.log(arr);
//expected output: (3) ["Boahs", "Bob", "Torbjorn"]
arr.shift();
console.log(arr);
//expected output: (2) ["Bob", "Torbjorn"]
```

The shift() method is removing the zeroeth index element, and returning it. I didn't include the return statement in the example above but it's returning 'Boahs', and removing it completely from the array. See how similar .shift() is to .pop();? Instead of removing the last indexed item you're removing the first. These can be very useful to use inside more complex loops which I'll get into on a future article. 




Finally we get to the .unshift() method! This method works exactly like .push(), but instead of adding an element to the end of an array, .unshift() is adding a new element to the beginning of an array. If you're appending multiple elements then you can add those inside the parameters, and they're inserted as a cunk at the beginning of the array.

```javascript
let arr = ['Donuts','Pie','Lemons','Pizza','Peaches]
console.log(arr);
//expected output: (5) ["Donuts", "Pie", "Lemons", "Pizza", "Peaches"]
arr.unshift('Pears');
console.log(arr);
//expected output: (6) ["Pears", "Donuts", "Pie", "Lemons", "Pizza", "Peaches"]
```


Hopefully this helps out anyone out their reading this! It's easy to remember all four of these methods when you realize that .unshift(), and .shift() are best friends with .push(), and .pop() - The only difference is which part of the array is being manlipulated! 


**— Boahs**
