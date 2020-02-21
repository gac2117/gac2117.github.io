---
layout: post
title:      "Golang Conditionals"
date:       2020-02-21 19:09:29 +0000
permalink:  golang_conditionals
---


This post will explain the basics of Golang conditionals.

### **If/Else Statements**

Conditional statements tell a program to execute different actions depending on whether a condition is true or false.
For example, if x is equal to 5 then do this. If not, then do something else.
That is a simple if/else statement. 

Here is what it looks like in code:

```
x := 5

if x == 5 {
  fmt.Println("x is equal to 5")
} else {
  fmt.Println("x is not equal to 5")
}
```

Here we have a variable called x set to the number 5.

To start the if/else statement, we use the keyword `if`. Then we write the expression that we want to evaluate as either true or false. So in our case, we want to know if x is equal to 5.

If it is true, then inside the curly brackets, we will write what should happen. For us, we want to print out the string "x is equal to 5".

If the expression is false, meaning x does not equal 5, then we use the keyword `else`. Then in the curly brackets we execute a different action. In our case, we want to print out the string "x is not equal to 5".

In order to execute this conditional statement, it needs to be inside the `main()` function:

```
func main() {
  x := 5

  if x == 5 {
    fmt.Println("x is equal to 5")
  } else {
    fmt.Println("x is not equal to 5")
  }
}
```

If we execute the code, the output should be "x is equal to 5".

Now let's change x to a different number, like 7. Then since x is not equal to 5, it should execute that else statement

```
func main() {
  x := 7

  if x == 5 {
    fmt.Println("x is equal to 5")
  } else {
    fmt.Println("x is not equal to 5")
  }
}
```

If we execute the code, the output should be "x is not equal to 5".

### **Else if statements**

We can add as many conditional statements as we want. All we have to do is use the keyword `else if`.

For example, let's say we want to check if x is greater than 10, less than 10, or equal to 10.

```
if x > 10 {
  fmt.Println("x is greater than 10")
} else if x < 10 {
  fmt.Println("x is less than 10")
} else if x == 10 {
  fmt.Println("x is equal to 10")
}
```

The first expression is checking if x is greater than 10. If true, then it will print out "x is greater than 10".

If false, it will go to the next expression, which is checking if x is less than 10. Again, if this is true, then it will print out "x is less than 10", but if false, it will go to the last expression.

The last expression is checking whether x is equal to 10.

Let's execute this code and see what we get if we set x to equal 15.

```
func main() {
  x := 15

	if x > 10 {
		fmt.Println("x is greater than 10")
	} else if x < 10 {
		fmt.Println("x is less than 10")
	} else if x == 10 {
		fmt.Println("x is equal to 10")
	}
}
```

If we execute the code, the output should be "x is greater than 10".

Okay now let's try a number that is less than 10, like 5:

```
func main() {
  x := 5

	if x > 10 {
		fmt.Println("x is greater than 10")
	} else if x < 10 {
		fmt.Println("x is less than 10")
	} else if x == 10 {
		fmt.Println("x is equal to 10")
	}
}
```

If we execute the code, the output should be "x is less than 10".

Now let's set x to equal 10:

```
func main() {
  x := 10

	if x > 10 {
		fmt.Println("x is greater than 10")
	} else if x < 10 {
		fmt.Println("x is less than 10")
	} else if x == 10 {
		fmt.Println("x is equal to 10")
	}
}
```

If we execute the code, the output should be "x is equal to 10".

Instead of an `else if` statement at the end, we could've used an `else` statement too because if x is not greater or less than 10, then it must equal 10:

```
if x > 10 {
  fmt.Println("x is greater than 10")
} else if x < 10 {
  fmt.Println("x is less than 10")
} else {
  fmt.Println("x is equal to 10")
}
```

If we execute the code, the output should still be "x is less than 10".

### **Switch statements**

But for complex conditionals, it is cleaner to use switch statements. A switch statement will run the first case equal to the condition expression. The cases are evaluated from the top down, and will stop once a case is executed. If none of the cases match, there is a default case that will be executed instead.

Let's write a switch statement now. 

Let's say a variable called 'month' is set to the numeric representation of a month. The switch statement will then print out the name of the month. 

So first let's declare a variable at the top called month and set it equal to 5 for now. 

```
  month := 5
```

To build our switch statement, we will use the keyword `switch` and then the expression that will be used against the cases. So in our case, it is the month.

```
  switch month {

  }
```

To create the different cases, we use the keyword `case` and then the conditional that needs to be evaluated as true. 
So in our case, we will need 12 cases to check all the months of the year. And then we need a default case just in case the month variable is set to a number that is not a month, like 0 or 13.

```
	switch month {
	case 1:

	case 2:

	case 3:

	case 4:

	case 5:

	case 6:

	case 7:

	case 8:

	case 9:

	case 10:

	case 11:

	case 12:

	default:

	}
```

Now what do we want do if one of these cases are true? We want to print out the name of the month. And for the default case, if the month variable is set to a number that is not 1-12, then we can print out a message saying "This is not a month".

```
	switch month {
	case 1:
		fmt.Println("January")
	case 2:
		fmt.Println("February")
	case 3:
		fmt.Println("March")
	case 4:
		fmt.Println("April")
	case 5:
		fmt.Println("May")
	case 6:
		fmt.Println("June")
	case 7:
		fmt.Println("July")
	case 8:
		fmt.Println("August")
	case 9:
		fmt.Println("September")
	case 10:
		fmt.Println("October")
	case 11:
		fmt.Println("November")
	case 12:
		fmt.Println("December")\	
	default:
		fmt.Println("This is not a month")
	}
```

If we execute the code, the output should still be "May".

And we change the value of month to a number other than 1-12, it should hit the default case and print out "This is not a month".

### **Here is the final code for all of the examples in this post**
```
package main

import "fmt"

func main() {
	x := 5

	if x == 5 {
		fmt.Println("x is equal to 5")
	} else {
		fmt.Println("x is not equal to 5")
	}

	if x > 10 {
		fmt.Println("x is greater than 10")
	} else if x < 10 {
		fmt.Println("x is less than 10")
	} else {
		fmt.Println("x is equal to 10")
	}

	month := 5

	switch month {
	case 1:
		fmt.Println("January")
	case 2:
		fmt.Println("February")
	case 3:
		fmt.Println("March")
	case 4:
		fmt.Println("April")
	case 5:
		fmt.Println("May")
	case 6:
		fmt.Println("June")
	case 7:
		fmt.Println("July")
	case 8:
		fmt.Println("August")
	case 9:
		fmt.Println("September")
	case 10:
		fmt.Println("October")
	case 11:
		fmt.Println("November")
	case 12:
		fmt.Println("December")
	default:
		fmt.Println("This is not a month")
	}
}
```
