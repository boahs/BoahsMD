---
title: "Weekly favorite Codewars challenges"
path: "/favorite_july2"
date: "2020-07-12"
coverImage: ""
author: "Boahs"
excerpt: '"Spoiler warning! CodeWars Solutions are listed in these posts!"'
tags: ["fundamentals", "strings", "regex", "codewars", "js", "learning", "7kyu"]
---

## Top codewars challenges of July week #2

This week I've encountered some fun codewars challenges. You'll notice I'll be doing a lot of `string` exercises - this is because I'm really into `strings` in general!

1. Borrower Speak (7kyu)

[Link to kata](https://www.codewars.com/kata/57d2ba8095497e484e00002e)

In this kata we're trying to implement a `function` create borrower speak. In the words of the kata:

"The borrowers are tiny tiny fictional people. As tiny tiny people they have to be sure they aren't spotted, or more importantly, stepped on.

As a result, the borrowers talk very very quietly. They find that capitals and punctuation of any sort lead them to raise their voices and put them in danger.

The young borrowers have begged their parents to stop using caps and punctuation."

So with this we know we have to:

1. Remove all punctuation

Easy enough? Well when they say "remove ALL punctuation" they mean everything. This includes:

1. Whitespace (spacing)
2. Uppercase
3. Even special characters such as \*\$%#^ etc...

Okay now we know what we need to do, so how do we set this function up?

```javascript
function borrow(s){
...
}
```

The first thing I'm going to do is create a variable called `regEx` and let the value contain all the punctuation we're going to be removing.

```javascript
function borrow(s) {
  let regEx = /[.,\/#?!$%\^&\*;:{}=\-_`~()\s]/g;
}
```

So we're capturing all punctuation inside our regex while using the `g` tag so it captures this globablly. We have our base built to remove all that garble so the little borrowers don't end up getting caught.

Nextly we're going to add yet another variable called `strip` to have the value of the parameter `s` with the `.replace()` method to find all that punctuation, and replace it with a new string.

```javascript
function borrow(s) {
  let regEx = /[.,\/#?!$%\^&\*;:{}=\-_`~()\s]/g;
  let strip = s.replace(regEx, "");
}
```

Perfect! Now we're replacing all the punctuation that the user would input, and returning that into a new string.

The absolute last step we need to do when approaching this problem is return the actual variable `strip` and use the `toLowerCase()` method to make everyone a bit quieter.

```javascript
function borrow(s) {
  let regEx = /[.,\/#?!$%\^&\*;:{}=\-_`~()\s]/g;
  let strip = s.replace(regEx, "");
  return strip.toLowerCase();
}
```

That'll do it! The borrowers can live in peace for now.

2. Numbers in strings (7kyu)

[Link to kata](https://www.codewars.com/kata/59dd2c38f703c4ae5e000014)

In this kata we're given a string that has only lowercase letters and numbers. Our task will be to compare the number groupings and return the largest number inside the string. An example:

`solve("gh12cdy695m1") = 695`

```javascript
function solve(s){
...
};
```

So we'll approach this with creating a single variable called ```number``` that uses the `s` parameter to `.match()` some regex. The regex we'll be using `/\d+/g` will be matching any digit equal from `[0-9]` while adding in the `greedy` `quantifier` and ending that with a `g` tag. 

```javascript
function solve(s){
let number = s.match(/\d+/g);
};
```

So once again - we have our building block to find any digit inside the string so the next logical step to find the highest number inside the string would be to `return` the `number` variable with the `Math.max()` method.

```javascript
function solve(s){
let number = s.match(/\d+/g);
return Math.max(...number);
};
```

You can see we're also using the `spread syntax` before number to return just the number without supplying any additional arguements. 

3. Alan Partridge II - Apple Turnover (8kyu)

[Link to kata](https://www.codewars.com/kata/580a094553bd9ec5d800007d)

In this kata we're determining if one parameter `x` squared is more than 1000, and if it is we need to `return` `'It's hotter than the sun!!'` else if it isn't we'll `return` `'Help yourself to a honeycomb Yorkie for the glovebox.'` `x` will be either a number or a string. Both are valid. 

```javascript
function apple(x){
  }
```
This kata was a little easier, and I managed to complete it all in one line.

So the logical thing to do would be to first square x and we can do that with the `Math.pow()` method. It needs to be greater than `1000` to return the first string so we'll build the base.


```javascript
function apple(x){
return Math.pow(x,2) > 1000
  }
```

You may notice we're already returning the `Math.pow()` method with the arguements being greater than 1000. Well now we can use a `terninary` operator to finish this up. 

```javascript
function apple(x){
return Math.pow(x,2) > 1000 ? `It's hotter than the sun!!` : 'Help yourself to a honeycomb Yorkie for the glovebox.'
  }
```

That solves this kata! 


4. Simple comparsion? (8kyu)

[Link to kata](https://www.codewars.com/kata/57f6ecdfcca6e045d2001207)

Another rather simple kata turned out to be one of my more favorable ones this week. Our task is to write a function that will compare two values, one will be a number and one will be a string. We'll need to `return` `true` if they are the same character regardless of data types, and `return` `false` if they are not. To make this challanege a bit more difficult we aren't allowed to use any of the following methods : 

`.toString()`

`.join()`

`.split()`

`.parseInt`

`Number()`

So lets move onto the function:

```javascript 
function add(a, b){
}
```

Our first notion would be to simply just compare these two arguments, and  that'll solve this.  

```javascript
function add(a, b){
  return a == b
}
```

But I wanted to have a more unique redundant aproach because I can. 

So we'll compare the arguements as above 

```javascript
function add(a, b){
  return a == b ? true : false;
}
```

while saying if `a == b` is true then we'll return our `terninary operator` to return if `true` is `true` or `false` is `false` :-). 

Okay - quick easy kata! Let's move on and go for another!

5. Hello World - Without Strings (7kyu)

[Link to kata](https://www.codewars.com/kata/584c7b1e2cb5e1a727000047)

In this kata we need to create a function `helloWorld` to `return` the `string` `Hello, World!` without using any raw strings. This will include using quotes, double quotes and template strings. 

So none of the below: 

```javascript
"Hello, World!"
'Hello, World!'
`Hello, World!`
```

So we'll aproach this kata using the `String` object to still have a string without using any quotes. We'll add some literal regex characters inside the parameters. 

So we set the `a` variable to equal the `string()` object.

```javascript
const helloWorld = () => {
let a = String(/Hello, World!/);
};
```

The next logical thing to do is using the `substring()` method to return the beginning of the string, and the end. The one thing we don't want to do though is return the actual regex `/.../` backslashes. So instead of using `substring(0,15)` we're going to return the `1` index, and the `a.length-1` index. 

```javascript
const helloWorld = () => {
let a = String(/Hello, World!/);
a = a.substring(1, a.length-1);
  return a;
};
```

This'll return the index starting at the 'H' and end at the '!' since we're removing ONE off the end from `a.length`

I enjoyed this kata a lot. I used a lot of regex in these solutions, huh? Regex seems to be PRETTY powerful. 

Hope you enjoyed the write up, and enjoy the rest of your day/night! 

**— Boahs**