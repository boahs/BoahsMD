---
title: "Weekly favorite Codewars challenges"
path: "/favorite_july1"
date: "2020-07-05"
coverImage: ""
author: "Boahs"
excerpt: '"Spoiler warning! CodeWars Solutions are listed in these posts!"'
tags: ["js", "learning", "regex", "strings", "oop", "spoilers", "7kyu", "8kyu", "codewars", "algorithmic challenges", "fundamentals"]
---

## Top codewars challenges of July week #1

I'm going to start posting my favorite codewars katas, and a small description on how they work every week - I'll try to maintain this pace to the best of my ability! If you're activily trying to solve katas be sure to check the blog tags for the kyu levels I'll be talking about! I <b>will</b> be posting solutions - so you might want to try to solve these on your own first! 

1. Fix My Phone Numbers!(7kyu) 

[Link to kata](https://www.codewars.com/kata/596343a24489a8b2a00000a2/javascript)

In this level 7kyu kata we're trying to impliment a ```function``` with one parameter ```(str)``` to fix a databases phonenumbers. Our task :

- Remove all whitespace
- Remove any random characters 
- Make sure the phone number is at least 11 digits
- Make sure the phone number starts with 0

If our ```str``` meets all these requirements we'll return it. Otherwise we'll return ```'Not a phone number'```.

The first thing we'll do is define some ```regex``` that only identifies numbers. 

```javascript
function isItANum(str) {
let regex = /[0-9]/g
}
```

Then we'll add in two new variables. ```a``` will be taking the ```str``` and using the ```.replace()``` method to take all unwanted characters spanning from a-z, and replacing that with an empty string. Note: We're removing whitespace this way as well by having the string completely empty. The next variable ```b``` will be matching our first variable with the ```regex``` variable with the ```.match()``` method, then with the ```.join()``` method we'll be joining that onto an empty string. 

```javascript
function isItANum(str) {
let regex = /[0-9]/g
let a = str.replace(/[a-zA-Z]/g, '');
let b = a.match(regex).join('');
}
```

Now we have our base to build onto and figure out if the ```str``` is valid or not. So finally we'll be adding a simple ```if else``` statement to do that. 

```javascript 
function isItANum(str) {
let regex = /[0-9]/g
let a = str.replace(/[a-zA-Z]/g, '');
let b = a.match(regex).join('');
 if (b.startsWith(0) && b.length === 11){
     return b;
     }else{
       return 'Not a phone number'
     }
}
```

In the above ```if else``` statement we're asking if ```b``` <b>starts with</b> 0 AND the length of ```b``` is 11 we'll return b. If it doesn't meet those requirements we'll simply return the string ```'Not a phone number'```

Voila! After going over my solution I do see we could of used a [ternary operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator) to solve this instead of the ```if else``` statement but I'm lazy, and not resubmitting it! 


2. Fun with ES6 Classes #1 - People, people, people

[Link to kata](https://www.codewars.com/kata/56f7f8215d7c12c0e7000b19/train/javascript)

In this level 8kyu kata we're trying to define a ```class``` called ```Person``` with the following properties:

- A constructor that accepts these four arguements - ```firstName```, ```lastName```, ```age```, ```gender```
- The constructor properties default with ```firstName: "John"``` ```lastName: "Doe"``` ```age: 0``` ```gender: Male```
- A ```method``` named ```sayFullName``` that has no arguements, and returns the full name. 
- a static method named ```greetExtraTerrestrials``` that accepts one parameter ```raceName``` and returns "Welcome to Planet Earth ```raceName```" 

I approached this kata in an older way instead of fully committing to the ES6 syntax. If you'd like to know more about the ES6 syntax on defining variables with default values please check [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

So the first thing we'll do is add the ```constructor``` inside the ```class```. 

```javascript
class Person {
  constructor(firstName,lastName,age,gender)
  {...}
}
```
We've added our properties. Note if I added the defaults in the ES6 syntax I'd added them in parameters after ```constructor``` like this : 

```javascript
class Person {
  constructor(firstName = 'John', lastName = 'Doe', age = 0, gender = 'Male')
  {...}
}
```
But I didn't, and went with another approach by using the ```||``` operator. 

Now that we have our ```constructor``` setup we'll define the properties using the ```this``` keyword.

```javascript
class Person {
  constructor(firstName,lastName,age,gender){
    this.firstName = firstName || "John";
    this.lastName = lastName || "Doe";
    this.age = age || 0;
    this.gender = gender || "Male";
  }
}
```

So we'll get our defaults requirements met doing this adding the ```or``` operator if the first value is ```false```. 

Next we'll add the ```sayFullName(){...}``` method using a template literal string so we can capture our property objects together cleanly.

```javascript
class Person {
  constructor(firstName,lastName,age,gender){
    this.firstName = firstName || "John";
    this.lastName = lastName || "Doe";
    this.age = age || 0;
    this.gender = gender || "Male";
  }
  sayFullName(){
    return `${this.firstName} ${this.lastName}`;
  }
}
```

So now that we've added this new method inside our class we can call this method, and it'll return the ```firstName``` and ```lastName``` given inputs, or defaults. 

Finally to finish this ```class``` up we're going to add a static method to return the alien greeting. 

```javascript
class Person {
  constructor(firstName,lastName,age,gender){
    this.firstName = firstName || "John";
    this.lastName = lastName || "Doe";
    this.age = age || 0;
    this.gender = gender || "Male";
  }
  sayFullName(){
    return `${this.firstName} ${this.lastName}`;
  }
  static greetExtraTerrestrials(raceName){
    return `Welcome to Planet Earth ${raceName}`;
  }
}
```

Just like that we've wrote the fully functional class! I really liked this one because it shows the importance of the ```this``` keyword. 


3. Say hello!

[Link to kata](https://www.codewars.com/kata/55955a48a4e9c1a77500005a)

In this kata we're simply writing a function that will greet a person by saying ```hello ${name}``` 

Our tasks:

- Return hello & the name if given
- Return null/nil/None if the input is empty

This level 7 kata was a little bit easier but still fun nonetheless. So first we take our function 

```javascript
function greet(name) {...}
```

Inside our function we're simply going to return a terinary operator to solve it. 

```javascript
function greet(name) {
  return name ? `hello ${name}!` : null;
}
```

What's exactly happening above? The function is returning the name to the first value ``` `hello ${name}!` ``` if the input is truthy. If the input is empty/falsy we're returning ```null```. That's it. I'll be honest...I'm a huge sucker for the terinary operator, and that's solely the reason I loved this kata. It's very ironic of me saying that considering the first kata I talked about could of used one instead of the ```if else``` statement ;) but I seriously do love them. 


4. Define a card suit

[Link to kata](https://www.codewars.com/kata/5a360620f28b82a711000047)

So in this kata we're setting suit value for the cards. We're given predefined data of the deck:

```javascript
deck = ['2♣','3♣','4♣','5♣','6♣','7♣','8♣','9♣','10♣','J♣','Q♣','K♣','A♣',
        '2♦','3♦','4♦','5♦','6♦','7♦','8♦','9♦','10♦','J♦','Q♦','K♦','A♦',
        '2♥','3♥','4♥','5♥','6♥','7♥','8♥','9♥','10♥','J♥','Q♥','K♥','A♥',
        '2♠','3♠','4♠','5♠','6♠','7♠','8♠','9♠','10♠','J♠','Q♠','K♠','A♠'];
```

So I approached this kata using an ```if else``` chain, and the ```.includes``` method to determine what suit returned to the symbol. 

```javascript
function defineSuit(card) {
  if (card.includes('♣')) {
    return "clubs";
  }
  else if (card.includes('♦')) {
    return "diamonds";
  }
  else if (card.includes('♥')) {
    return "hearts";
  }
  else if (card.includes('♠')) {
    return "spades";
  }
};
```

Pretty self explanatory we're using the ```card``` parameter to call the ```.includes()``` method and figure out which symbol matches each suit, and ```returning``` that data back. 

As I said before I'll do my best to keep up with weekly blogs specifically about my favorite katas I've done that week, considering I use codewars daily it shouldn't be an issue with content. The only thing that would halt a weekly post would being extremely busy! Considering I'm starting my first week of Lambda bootcamp tomorrow on July 6th I reckon being busy will be a given! I'll still try to update these though. Thanks for reading! 

**— Boahs**
