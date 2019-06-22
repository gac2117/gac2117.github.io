---
layout: post
title:      "Scope and Hoisting"
date:       2019-06-22 19:11:16 -0400
permalink:  scope_and_hoisting
---


When learning JavaScript for the first time, it is important to learn the older JavaScript versions as well as the newest version, ECMAScript 2015 (or ES6). If we only focus on ES6, then we will not be able to read or understand most of the JS in programs since they were written well before 2015. However, moving forward, as you write your own JS in programs, you should implement ES6 standards.

With that in mind, I will introduce the basic concepts of **scope** and **hoisting**.

### JavaScript Scopes:

Before ES6, JS only had two types of scope: **Local Scope** and **Global Scope**

#### Local Scope:
When you create a function, variables that are declared inside the function become local to the function. Therefore these variables can only be accessed from within the function.

```
// Outside of the function, I cannot access the variable 'cityName'

function myTrip() {
   var cityName = “Seoul”;
   // Inside this function, I can use the variable 'cityName'
}
```

These local variables are created when a function starts, and deleted when the function ends. 

#### Global Scope:
Variables that are declared outside a function has global scope. This means they can be used in any function or script on the page.

```
var cityName = “Seoul”;
// all codes can access the variable 'cityName'

function myTrip() {
   // I can use the variable 'cityName' inside this function too
}
```

But with ES6, it introduced a third type of scope, **Block Scope**, along with two new variable keywords, `let` and `const`, that changed a lot of things! 

But first, a little bit about **hoisting.**

### JavaScript Hoisting:
 A side note about variable declaration and initialization. 
```
var cityName;            // this is declaring a variable
cityName = “Seoul”;      // this is initializing a variable
var cityName = “Seoul”;  // this is declaring and initializing a variable.
```

Technically a variable can be declared after it has already been used. This is possible because of “**hoisting**”. No matter where you declared the variable in your code, JavaScript will automatically “hoist” or move up the declaration to the top of the current scope.

```
cityName = “Seoul”;

console.log(cityName);

var cityName;
```

will give the same result as: 

```
var cityName;

cityName = “Seoul”;

console.log(cityName);
```

However, only variable *declarations* are hoisted, not *initializations*.

Therefore, 
```
var cityName = “Seoul”;

console.log(cityName + “, “ + countryName);

var countryName = “South Korea”;
```

will result in `countryName` being undefined because only the declaration of `var countryName` was hoisted, and not the initialization (`= ”South Korea”`)

So it is the same thing as writing:
```
var cityName = “Seoul”;

var countryName;

console.log(cityName + “, “ + countryName);

countryName = “South Korea”;
```

It is clearer in this second example what was wrong. We declared a variable but didn’t assign it any value until afterwards. That’s why it was undefined.

However, ever since ES6, we now declare variables using `let` and `const`. These variables are NOT hoisted by JS. Therefore, it is a good practice to always declare all variables at the beginning of every scope yourself instead of letting JS hoist them (or NOT hoist them) automatically.

#### Block Scope:
Now, back to scopes, ES6 introduced a new scope called **Block Scope**. This means variables that are declared inside a **block {}** cannot be accessed outside of the block. 

Variables that are declared with the `var` keyword cannot have Block Scope. Therefore `var` variables that are declared inside a block can still be accessed and redeclared outside of the block! 

For example,
```
var i = 5;

for (var i = 0; i < 10; i++) {
  // some code to execute 
}
// Here i is 10 because the variable was redeclared inside the loop!
```

Therefore, it is a good idea to always declare variables using `let` and `const` since they do have block scope. 
```
let i = 5;

for (let i = 0; i < 10; i++) {
   // some statements
}
// Here i is still 5 because the variable declared in the loop did not redeclare the original variable i outside of the loop. 
```

##### A little more about the variable keywords and redeclaring variables:

Redeclaring `var` variables is allowed anywhere in a program. This can become a mess quickly!
```
var x = 1;
// x is 1

var x = 2;
// now x is 2!
```

Redeclaring `var` variables with `let` is not allowed if you are in the same scope.
```
var x = 1
// x is 1

let x = 2
// this is not allowed

{
  var x = 2
  // inside this block you can redeclare x to be 2
   
	let x = 3
	// but this is not allowed since it is inside the same block scope
}
```

The same goes for redeclaring `let` variables with `let`, as well as redeclaring `let` variables with `var`. If you are in the same scope, you cannot redeclare it. 

However, you can redeclare `let` variables in different scopes
```
let x = 1
// x is 1

{
    let x = 2
    // in this block, x is 2
}
// back outside the block, x is 1

{
    let x = 3
    // inside a different block, x is 3
}
```

As for `const` variables, they behave like `let` variables except that they *cannot be reassigned*.
```
const x = 1;
// x is 1

x = 2;
// this will give an error. x will forever be 1.
```

Also different from `let` variables, `const` variables *must be assigned a value* when declared.
```
const x;  // this is not allowed
const x = 1;  // this is how it must be done
```

However `const` variables have Block Scope, just like `let` variables, so 
```
const x = 1;
// x is 1

{ 
    const x = 2;
    // inside this block, x is 2
}
// back outside the block, x is still 1
```


