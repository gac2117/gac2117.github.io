---
layout: post
title:      "Golang Loops"
date:       2020-02-25 16:48:38 +0000
permalink:  golang_loops
---

This post will explain the basics of Golang conditionals.

### **`for` Loop**

There are many types of loops in programming languages, but in Golang there is only one: the `for` loop. Basically, the `for` loop will repeatedly execute code inside the block for a specific number of times.

### **Syntax of `for` loop**

```golang
for initialization; condition; post{

}
```

We start by using the keyword `for` and then the initialization statement. This is a simple statement, like variable declarations. It is executed before the first loop or iteration.

Next is the condition statement. This is a boolean expression that is executed before every iteration. It is checking whether we should run the loop again or not. If the boolean expression is true, then the loop executes. If it is false, then it stops.

Finally there is the post statement. This is executed after every iteration.

We separate these statements using a semi-colon (;). Let's build a simple `for` loop now.

### **`for` loop Example**

#### Change the initialization statement:

```golang
for i := 0; condition; post{

}
```

For the initialization statement, we are going to declare a variable 'i' and set it to 0. That will serve as our counter.

#### Change the condition statement:

```golang
for i := 0; i < 5; post{

}
```

For the condition statement, we are going to run the loop as long as 'i' is less than 5. So basically it will run 5 times.

#### Change the post statement:

```golang
for i := 0; i < 5; i++{

}
```

For the post statement, we are going to increment 'i' by 1 at the end of every loop.

Now, for the body of the loop, what do we want to do 5 times? Let's say we want to print out "Coding is fun!".

```golang
for i := 0; i < 5; post{
  fmt.Println("Coding is fun!")
}
```

If we execute the code, the output should be:
```
Coding is fun!

Coding is fun!

Coding is fun!

Coding is fun!

Coding is fun!
```

Okay well let's try to see exactly how this is working. Instead of printing "Coding is fun" 5 times, let's print what the variable 'i' is in every loop.

```golang
for i := 0; i < 5; post{
  fmt.Println(i)
}
```

If we execute the code, the output should be:

```
0

1

2

3

4
```

Notice what the loop is doing. First, before the loop executes, 'i' is 0. After the loop executes, 'i' is incremented by 1 so it is 1. That is still less than 5, so the loop executes and prints out 1. Then it is incremented by 1 again, making it 2. That is still less than 5, so the loop executes.

This keeps repeating until 'i' is no longer less than 5. So that's why it ends with printing out 4.

### **FizzBuzz Example**

This example is a variation of a popular coding challenge that is actually given in technical interviews. This is an easier version of it. Usually it involves printing out numbers 1 to 100. Every number divisible by 3 will print out "Fizz", every number divisible by 5 will print out "Buzz", and every number divisible by 15 will print out "FizzBuzz".

But for our purposes, we only have to print out "FizzBuzz" if the number was divisible by 4.

First, let's set up our `for` loop.

```
for i := 1; i<=30; i++ {

}
```

We will set 'i' to 1 so it starts printing out the numbers starting with 1. We will keep running the loop until it equals 30. And we will increment 'i' by 1 every time the loop ends.

We will need to set up an `if/else` statement inside the loop to check if the number is divisible by 4 each loop.

```
for i := 1; i<=30; i++ {
  if {

  } else {

  }
}
```

In order to know if a number is cleanly divisible by another number, the remainder must be 0. We check for this using the modulus operator %.

```golang
for i := 1; i<=30; i++ {
  if i%4 == 0{

  } else {

  }
}
```

Here we are saying, if we divide 'i' by 4 and there is no remainder, then we know this is cleanly divisible by 4. That means we need to print out "FizzBuzz", so let's add that to the body of the if statement.

```golang
for i := 1; i<=30; i++ {
  if i%4 == 0{
    fmt.Println("FizzBuzz")
  } else {

  }
}
```

For the rest of the numbers, we want to just print out the number. So in the body of the else statement, let's do that.

```golang
for i := 1; i<=30; i++ {
  if i%4 == 0{
    fmt.Println("FizzBuzz")
  } else {
    fmt.Println(i)
  }
}
```

If we execute the code, the output should be:
```
1

2

3

FizzBuzz

5

6

7

FizzBuzz

9

10

11

FizzBuzz

13

14

15

FizzBuzz

17

18

19

FizzBuzz

21

22

23

FizzBuzz

25

26

27

FizzBuzz

29

30
```

Here we see 1, 2, 3, and then where there should be 4, we have the word "FizzBuzz". Then it continues on 5, 6, 7, and then "FizzBuzz". If you check all the way down, you will see that it printed "FizzBuzz" every 4th time. Finally it ended at 30.

### Here is the final code for all of the examples in this post
```
package main

import "fmt"

func main() {
	for i := 0; i < 5; i++ {
		fmt.Println("Coding is fun!")
	}

	for i := 0; i < 5; i++ {
		fmt.Println(i)
	}

	// FizzBuzz example
	for i := 1; i <= 30; i++ {
		if i%4 == 0 {
			fmt.Println("FizzBuzz")
		} else {
			fmt.Println(i)
		}
	}
}
```

