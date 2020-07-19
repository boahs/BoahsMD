---
title: "Weekly favorite Codewars challenges"
path: "/favorite_july3"
date: "2020-07-19"
coverImage: ""
author: "Boahs"
excerpt: '"Spoiler warning! CodeWars Solutions are listed in these posts!"'
tags:
  [
    "fundamentals",
    "arrays",
    "array methods",
    "strings",
    "regex",
    "codewars",
    "js",
    "learning",
    "7kyu",
    "8kyu",
  ]
---

## Top codewars challenges of July week #3

This week has been awesome! I've learned some newer things allowing me to complete more 7kyu rated challenges! I've learned how to properly pass the `.map()` method, and the `.reduce()` method! I've also learned these open up so many doors to array manlipulation, and getting our much needed solutions. Quite honestly the last time I remember learning something as powerful as these two methods was the oh so powerful `regex`! `.Filter()` is next on the list of knowledge but that'll have to be saved for this week. Oh before I begin with the challenge reviews I'd also like to give an honorable mention to `arrow functions` these seemed to come hand in hand with learning some of the more advanced array methods!

1.  Use map() to double the values in an array - (7kyu)

[Link to kata](https://www.codewars.com/kata/53951fff369894e4f10007a9)

In this kata we're taking a function we defined as `double()` to return a new `array` with each value twice as large as the corresponding value passed in the array. Our solution needed to use `map()` - I chose this kata due to get more experience with the `map()` method.

So let's take our empty function

```javascript
function double(array) {
  // Use array.map() to return a new array with each value twice
  // as large as the corresponding value in the passed in array.
}
```

and of course an example so you're positive on what we're trying to achieve

```javascript
const someNumbers = [1, 2, 10, 57];

double(someNumbers); // should return [2,4,20,114]
```

So the first thing to do is think about how we're going to take our parameter `array` and return it to double the values. This is where `map()` becomes a superpower.

```javascript
function double(array) {
  return array.map(multiply);
}
```

The first thing we'll do is return the orginal `array` with the `map()` and use `multiply()` as our callback. Since the kata required us to double the values we'll simply use an `arrow pointer` to have `multiply()` point towards our logic.

```javascript
function double(array) {
  return array.map(multiply => multiply * 2);
}
```

Huzzah! The results will double all the values of the supplied argument.

2. Use reduce() to calculate the sum of the values in an array (7kyu)

[Link to kata](https://www.codewars.com/kata/532b4057484b0e58e8000766)

For this kata we're creating the function `sum(arr)` to return the sum of the values passed in an array. Our solution ofcourse must use the `reduce()` method for our solution to be valid.

```javascript
function sum(array) {
  // Use array.reduce() to find and return the
  // sum of the values in array.
}
```

```javascript
var someNumbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

sum(someNumbers); // should return 55
```

This being the actual first time I've used the `reduce()` method got me extra stoked since it actually clicked in my brain on why it works, and when to implement this method! I may of got a little too excited but oh well these advanced array methods are the cats meow!

So for the `reduce()` method to be valid we must execute a `reducer` function that we provide so it'll manipulate each element of the array and result in a single output value.

The first thing we're going to have to do is create a `const reducer` so let's get on with it.

```javascript
function sum(array) {
  const addAll = (addAll, array) => addAll + array;
}
```

So we're naming our reducer `addAll` with the parameters of `addAll` and the `array` we're changing. This is pointing towards the logic which simply adds `addAll` to each element of the `array`. I hope that makes sense!

```javascript
function sum(array) {
  const addAll = (addAll, array) => addAll + array;
  return array.reduce(addAll);
}
```

We'll then return our `array` calling the `reduce` method with the parameter `addAll` :

```javascript
const boahsArray = [1, 2, 3, 4, 5];
```

```javascript
function sum(array) {
  const addAll = (addAll, array) => addAll + array;
  return array.reduce(addAll);
}
```

```javascript
sum(boahsArray);
// result = 15
```

Would ya look at that? It works! I'm beyond excited to move onto the `filter()` method ASAP... I can already see these advanced array methods are extremely powerful in what they can return.

3. Random case (7 kyu)

[Link to kata](https://www.codewars.com/kata/57073869924f34185100036d)

This kyu is asking us to write a function that will randomly upper and lower characters inside a given `string`. This function will work within the basic ASCLL characters so that it's not extremely complicated.

The first thing we're going to have to do is make our string an `array` so that we're able to manipulate the characters without getting too complex then after we have our `array` of `substrings` we're going to go ahead and throw in a beautiful `map()` as well :

```javascript
function randomCase(x) {
return x.split('').map((y)

}
```

Alright. Step by step is how you solve these problems without going crazy so we're getting some where. We now have our `string` being returned as the `array` and using `map()` with `y` as our callback. So we need this to point towards some logic to actually randomly case our characters. Let's get on with that!

```javascript
function randomCase(x) {
return x.split('').map((y) => Math.round(Math.random())

}
```

Alright! We're getting places. We're now pointing our callback towards the two `Math` methods. Firstly to round our random number to always be a 0 or 1. The reason I did it this way was to not get results like 0.34...0.5....0.62...etc and have to use more conditions than I already have.

So can you guess what we're going to throw in next? Did you guess a terinary operator? Because if you did you're correct! We're going to say if the randomized Math.round is true we're turning `toUpperCase()` and if not return a `toLowerCase()` then we'll be joining this `array` back into it's most elegant form of a `string` with `join()`.

```javascript
function randomCase(x) {
  return x
    .split("")
    .map(y => (Math.round(Math.random()) ? y.toUpperCase() : y.toLowerCase()))
    .join("");
}
```

There we have it! Wanna test it out for fun? No?? Too bad! I do!

```javascript
randomCase("There we have it! Wanna test it out for fun? No?? Too bad! I do!");
// result 1 => "ThEre we HAVe it! waNnA TeST it OUT For fUN? no?? toO bAD! I do!"
// result 2 => "tHere WE Have IT! waNna TEsT IT ouT FoR FuN? nO?? tOO bAd! i dO!"
// result 3 => "THEre wE HAvE it! wAnNa TEst it out foR FUN? No?? tOO bad! i Do!"
// result 4 => "THERe wE havE it! wAnnA TeSt IT OuT fOR fUN? NO?? TOO Bad! I Do!"
```

4. Simple Fun #176: Reverse Letter (7 kyu)

[Link to kata](https://www.codewars.com/kata/58b8c94b7df3f116eb00005b)

This kata is asking us when given a string we'll need to reverse it omitting all non-alphabetic characters.

Here are some good examples :

`For str = "krishan", the output should be "nahsirk".`

`For str = "ultr53o?n", the output should be "nortlu".`

Our input is a string, and our output will be a string.

```javascript
function reverseLetter(str) {
    ...
}
```

Our first step is to create our `variable`, or in most cases a `const`. I didn't use a `const` in this solution but to my understanding it is considered best practice to use a `const` when you're able to. Anyways to do this we're going to let the value of our `variable` be using the `replace()` method to intake some `regex`.

```javascript
function reverseLetter(str) {
  let unwanted = str.replace(/[^a-zA-Z]+/g, "");
}
```

If this regex looks confusing to you then don't worry...all regex looks confusing. That's why we have resources like regex 101! I'll explain what it's doing anyways. We're using a `^` global `flag` to assert the position to start at the beginning of our line. We're then taking our `array` of letters `[a-zA-Z]` which returns all characters spanning from a to z lowercase, and uppercase. At the end outside our `array` we're using the `+` `quantifier` to match between one, and unlimited times. At the end of our `regex` we're adding the `g` `flag` to tell our function we want this `regex` to be called GLOBALLY!

Now we have our base built! We're going to want to use the `reverse()` method but how can we with a string since the `reverse()` method only intakes arrays? Did ya guess using `split()`? If you did you're correct!

```javascript
function reverseLetter(str) {
  let unwanted = str.replace(/[^a-zA-Z]+/g, "");
  return unwanted
    .split("")
    .reverse()
    .join("");
}
```

So we're using `split()` on our unwanted `variable` to create the new `array` of `substrings` then throwing in the `reverse()` method and then using `join()` to return the string.

Voila!

I am so ecstatic for anyone that may pick up something new from these blog posts! I hope you learned something new with it because I sure did. I promise we aren't going to turn these blog posts into 'code wars challenges!' only. I've just been so busy with the bootcamp I've been attending, and honestly having no time to do anything besides programming. I'm excited for the future, and what we'll achieve! Thanks for reading, and see you next time!

**— Boahs**
