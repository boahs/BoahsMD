---
title: "Understanding .Map(), .forEach() and .filter() ES6 style"
path: "/advancedArrayMethods"
date: "2020-07-24"
coverImage: ""
author: "Boahs"
excerpt: '"Level up your development skills with these array methods!"'
tags: ["array", "learning", "methods", ".map",".filter","ES6"]
---

## Advanced array methods - .map() .forEach() and .filter()

---
### Using for loops
Let's start this post off using a `for` loop so it'll be easier to understand exactly what we're doing when we get to the actual array methods `.map()` and `filter()`. Typically we'll use a `for` loop to iterate over every item in an array. An example would be to lowercase every string in an array:

```javascript
const strArr = ['JORDAN', 'COLIN', 'GARY', 'BOAHS', 'TIM', 'TRAVIS', 'BRENT', 'MATT'] // Our old array
const lowerCase = []; //We're creating an empty array to throw our new items into. 

for (let i=0; i<strArr.length; i++){   
    lowerCase.push(strArr[i].toLowerCase());
}
console.log(strArr) //result: ["JORDAN", "COLIN", "GARY", "BOAHS", "TIM", "TRAVIS", "BRENT", "MATT"]
console.log(lowercase) //result: ["jordan", "colin", "gary", "boahs", "tim", "travis", "brent", "matt"]
```

Incase you're rather new to javascript I'll explain exactly what's going on here. We're taking our for loop, and running it over the `strArr` array items. The `i=0` is our initial expression, `i<strArr.length` is saying we want our loop to end on the last item of our array. The `.length` is the entire length of the array and we're looping until we hit that point. The `i++` is our increment expression which is simply just telling our loop to go iterate through the array 1 by 1. Note: `++` is like saying `i + 1`! Now we're using the `.push()` method to add our `strArr` items into our `lowerCase` array. Lastly the `.toLowerCase()` is simply a built in string method to transform our items to lowercase characters. 

---
### Using .map()

Now this will bring us to using our first array method to make this much shorter and cleaner using `.map()` which creates a new array using the logic we provide: 

```javascript
const strArr = ['JORDAN', 'COLIN', 'GARY', 'BOAHS', 'TIM', 'TRAVIS', 'BRENT', 'MATT'] 
const mapWay = [];

strArr.map(lowerThese => mapWay.push(lowerThese.toLowerCase()));

console.log(strArr) //result: ["JORDAN", "COLIN", "GARY", "BOAHS", "TIM", "TRAVIS", "BRENT", "MATT"]
console.log(mapWay) // result : ["jordan", "colin", "gary", "boahs", "tim", "travis", "brent", "matt"]
```

Wow look how much less code we had to write to get the exact same results! I think that's pretty awesome. Let's go over exactly what's going on here. The first thing we're doing is taking our orginal array `strArr` and applying `.map()` to take it, and preform the logic. `.map()` will take a `callback` which in our case is `lowerThese` and point it towards our logic. We can use anything as our callback...I just decided to use `lowerThese` for better readability. So we're taking our callback as an `arrow function` and pushing `lowerThese.toLowerCase()` into `mapWay`! This in my opinion is a much better way to get our results for this specific use case. When we're using `.map()` it will create a new array using our callback just to be clear - this is what we're pushing into mapWay. It will not change the values of our old array at all either - this is the entire point of using a `callback` to return our new array! 

---
### Using .forEach()

Our second method `.forEach()` will function exactly like our `for` loop except it'll require fewer words:


```javascript
const strArr = ['JORDAN', 'COLIN', 'GARY', 'BOAHS', 'TIM', 'TRAVIS', 'BRENT', 'MATT'] 
const forEachWay = []; 

strArr.forEach(lowerThose => forEachWay.push(lowerThose.toLowerCase()));

console.log(strArr) //result: ["JORDAN", "COLIN", "GARY", "BOAHS", "TIM", "TRAVIS", "BRENT", "MATT"]
console.log(forEachWay) // result : ["jordan", "colin", "gary", "boahs", "tim", "travis", "brent", "matt"]
```


Our `forEach()` method is 'automatically' looping through the array items for us. So it's handling the initial expression for us while also handling the increment expression as well. So it's taking our callback `lowerThose` and iterating over every item in `strArr` to transform the characters to lowercase. This is almost the same way of using a `for` loop but with the `forEach()` we're creating cleaner code while also making it a bit more readable. The difference in our `forEach()` method and `.map()` method is that our `forEach()` method is NOT creating a new array so we must create the new array `forEachWay` to push our logic into. The value for `forEach()` will be undefined, and `.map()` will actually return a new array with the transformed elements. I'll create an example below to demostrate this: 

```javascript
const strArr = ['JORDAN', 'COLIN', 'GARY', 'BOAHS', 'TIM', 'TRAVIS', 'BRENT', 'MATT'];

strArr.map(lowerThese => lowerThese.toLowerCase());
//Result : ["jordan", "colin", "gary", "boahs", "tim", "travis", "brent", "matt"]
strArr.forEach(lowerThose => lowerThose.toLowerCase());
//Result : undefined
```
---
### Using .filter()

The last method I'll be going over on this post is `.filter()`. It'll allow us to process all the items in our array while filtering specific ones with the conditions we provide: 

```javascript
const strArr = ['JORDAN', 'COLIN', 'GARY', 'BOAHS', 'TIM', 'TRAVIS', 'BRENT', 'MATT'];

const filteredNames = strArr.filter(filteredNames => filteredNames.length > 5)
//console.log(filteredNames);
//Result : ["JORDAN", "TRAVIS"]
```

Pretty neat, right? So what we're doing here is creating a new array with all the elements in our orginal array `strArr` but only passing those items inside that are greater than 5 character length. Our `callback` is pointing towards our logic and then doing exactly that. A note to keep down is that our `callback` is only returning items that are `true` while the rest of the items are skipped. We aren't mutating the orginal array either since our `callback` is returning our new logic onto our `filteredNames` constant. 

---------

Hope all of this made sense! I know there will be room for improvement on explaining how specific JS methods work so I'll keep practicing with these blog posts until I'm excellent at doing so! Once you understand how to use these advanced array methods inside your daily code you'll see how powerful they really are! I know when I learned about these it brought back the same feeling as learning regular expressions did. "Oh these can do anything!" 

Take care and have a good one!

**— Boahs**
