---
title: "Best practices"
path: "/best_practices"
date: "2020-06-22"
coverImage: ""
author: "Boahs"
excerpt: '"Excellent code is easy to understand and maintain..."'
tags: ["js", "learning", "fundamentals", "best practices"]
---

## Naming conventions 

When you're writing your javascript code it's very important to follow standard practices.
It'll allow yourself, and anyone else to: 
* Understand your code better
* Find, and isolate bugs faster
* Refactoring will be easier
* Reusing the code will be easy to implement. 

## Short & readable variable and function names.

Nothing is worse than starting a project and writing a sloppy mess. You may come back to this code in the future and think "What is even happening? I wrote this?". Past you had wrote three very important variables named ```c2``` , ```c4```,and ```c9```. 

Throw in a couple more

```thisIsTheIncrementForOurForLoopWhichSpansFromOneHundredToTwoThousand``` 

or 

```createNewUserIfAgeIsOverEightTeenAndDoorIsClosed``` 

Just like that you have an unreadable disorganized mess. A great variable name will be easy to understand while still giving you a prompt idea of how they work too. A function called ```isLegalGamblingAge()``` will make a heap more sense than ```overTwentyOne()``` due to the legal gambling age being different depending what country you're referring to, and the fact that their are other things than gambling that are limited by age. 

## Optimize loops

When you're writing a loop a very common mistake is forcing the compiler to read the entire length of an array: 

```javascript
let birdClassification = ['Parrots','Columbidae','Owls','Hummingbirds','Finches','Penguins'];
for(let i=0;i<birdClassification.length;i++){
  doSomething(birdClassification[i]);
}
```

Everytime the loop above is called javascript will read the entire length of ```birdClassification``` which will result in slower loops. Avoiding this is as easy as creating a new variable to store the ```.length``` of the array:

```javascript
let birdClassification = ['Parrots','Columbidae','Owls','Hummingbirds','Finches','Penguins'];
let all = birdClassification.length;
for(var i=0;i<all;i++){
  doSomeThingWith(birdClassification[i]);
}
```

## Modularized functions 

Create your functions that have one clear objective so it's easier for other developers to debug, and change up your code without having to read through a ton of code creating a garbled muddle:

```javascript
function findBiggestDifference(arr) {
  let arrLength = arr.length;
  let currentMax = -Infinity;
  let currentMin = Infinity;
  for(let i = 0; i<arrLength; i++){
    if (currentMax < arr[i]) currentMax = arr[i]
    if (currentMin > arr[i]) currentMin = arr[i]
  }
  return currentMax-currentMin;
}
```
Here is the modular version:

```javascript
function findBiggestDifference(arr){
    let max = findMax(arr);
    let min = findMin(arr);
}

function findMax(arr){
    let arrLength = arr.length;
    let currentMax = -Infinity;
    for(let i=0;i<arrLength;i++){
        if (currentMax < arr[i]) currentMax = arr[i]
    }
    return currentMax;
}

function findMin(arr){
    let arrLength = arr.length;
    let currentMin = Infinity;
    for(let i=0;i<arrLength;i++){
        if (currentMin > arr[i]) currentMin = arr[i]
    }
    return currentMin;
}
```

You'll probably hear "If it isn't short then you're doing it wrong." While this can be true for some aspects inside programming this <i>isn't always</i> true. With the modular version the you know they're two functions that finds the maximum, and minimum values.  

## Ternary Notation

Conditions can be shortened using 'ternary notation' which can efficiently replace several lines of ```if else``` statements. It simply will verify if a condition is truthy, or falsy then will carry out an operation based on the state of the condition. 

Using an ```if else``` statement we have: 

```javascript
let christmas = true;

if(christmas){
    return(`It's christmas!`)
}else{
    return('invalid day')
   }
```

Using a ternary operator will result in this:

```javascript

let christmas = true; //condition
return (christmas ? `It's christmas!` : 'invalid day')

// '?' means IF 
// ':' means ELSE
```

## Commenting out your code

Comments inside code are your messages that other humans can read without it interfering with the actual code. This can also apply to yourself coming back several months later, and working on the same code! You might of heard 'Good code can, and should explain itself." but the flaw in this arguement is that the explanation can be subjective. You simply can't expect every dev understand what code is doing what functions. The trick is <i>moderation</i>! 

Actually commenting out old code you replace in the future is common practice, and is a neat trick that will help you debug code.  

## Avoid globals

Global variable and function names are always a bad idea. This is because every JS file you're including in the page will run in the same scope, and some scripts may overwrite your current variables/functions. 

There are a plenty of workarounds to avoid using globals - Let's assume you have two functions and a variable like this: 

```javascript
let start = Date.now()
function myConfig(){...}
function resetCounter(){...}
```

These function names are very common names that <b>will</b> be overwritten. Instead writing these inside an object literal will produce valid and safe code:

```javascript
let myNameSpace = {
    start:Date.now();
    myConfig:function(){...},
    resetCounter:function(){...},
}
```

This will work properly but their can still be issues. When you're calling the functions, or trying to change the variable value you'll need to use the main object with dot notation: ```myNameSpace.start```, and so on. This might get monotonous though. Instead we could wrap the entire thing inside an anonymous function, and protect the scope that way:

```javascript
myNameSpace = function(){
  let start = Date.now();
  function myConfig(){...}
  function resetCounter(){...}
}();
```

Now we're faced with the issue of nothing being available from the outside anymore. We can fix that though by wrapping the things we want to make public inside a ```return``` statement:

```javascript
myNameSpace = function(){
  let start = Date.now();
  return{
    myConfig:function(){...}
    resetCounter:function(){...}
  }
}();
```

Now this brings up the issue once again of having to change syntax, and linking together things. We can instead use a 'module pattern': 

```javascript
myNameSpace = function(){
  let start = Date.now();
  function myConfig(){...}
  function resetCounter(){...}
  return{
    myConfig:myConfig,
    resetCounter:resetCounter
  }
}();
```

See what changed? We're using return pointers to what we want to accomplish. It'll make it easier to call functions, and access the desired variables from other places without having to go through the ```myNameSpace``` name.  Calling ```myNameSpace.resetCounter()``` will now invoke the ```resetCounter()``` method. 

This will keep everything in your package squeaky clean, and make things easier to to modifiy in the future.

**— Boahs**




