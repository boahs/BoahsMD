---
title: "Loops...Loops...Loops"
path: "/Loops"
date: "2020-06-17"
coverImage: ""
author: "Boahs"
excerpt: '"In JavaScript we have many different types of loops. Today we'll look at the for...of statement"'
tags: ["js", "loops", "learning"]
---
## Understanding loops 

```javascript
for (let i=0; i<5;i++){
    console.log(`I'm looping!`, i);
}
```

Above we have one of five types of loops in javascript, and It'll repeat the code inside the block exactly five times. Let's see how it's working exactly.

```javascript
for (let [initialExpression]; [condition]; [incrementExpression]){
    [statement]
}
``` 

- The <b>initializing expression</b> is declared 
- The <b>condition</b> is evaluated, and if it returns <i>true</i> the initial statement will execute. If <i>false</i> the loop will terminate
-  The statement executes! To execute multiple statements, we use a <b>block statement</b> <i>{...}</i> to group these <b>statments</b>
- If the update expression is present the [incrementExpression] is executed. 

Are you wondering what the [incrementExpression] did? In javascript adding '++' behind our variable we declared 'i' will add one to it. So having i++ it's incrementing our variable <b>i</b> by one until it's completed that task five times. 

Alright let's return back to the previous example: 

```javascript
for (let i=0; i<5;i++){
    console.log(`I'm looping!`, i);
}
```
We declared our initial expression to start at 0. It'll check that <i>i</i> is less than <i>5</i>, and if this is true the loop will increment <i>i</i> by one each pass through our loop. Our loop has logic, and knows when to complete! 