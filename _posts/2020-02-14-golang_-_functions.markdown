---
layout: post
title:      "Golang Functions"
date:       2020-02-14 14:26:18 -0500
permalink:  golang_-_functions
---


This post will explain the basics of Golang functions.

### **Syntax for Functions**

Functions are blocks of code or statements that give the user the ability to reuse the same code.
These statements will perform a specific task and then return the results to the user.
Sometimes a function may not return anything.

To create a function, you must first declare it using this syntax:

```golang
func function_name(parameterName type)
```

To declare a function, use the keyword `func` and then the _function name_ followed by a set of parentheses.
If the function requires any parameters, list them inside the parentheses by first typing the _name of the parameter_ and then the _data type_ of the parameter.

After the closing parentheses, if the function returns any values, you need to write the _data type of the return value_:

```golang
func nameOfFunction(parameters type) type
```

Then open a set of curly brackets. Inside the brackets, you will write the code for the function:

```golang
func nameOfFunction(parameters type) type {
  // function body code
}
```

If the function has a return value, make sure you use the keyword `return` and then the _value_ that is being returned. The value should be the data type that we specified earlier.

```golang
func nameOfFunction(parameters type) type {
  return value
}
```

### **Example of a funcation**

Let's do an example now. 

Let's create a function that will take in a person's name and return "Happy Birthday \_\_\_!"
So let's call the function 'birthday' and it will take in a parameter of someone's name, which is a string.

```golang
func birthday(name string)
```

This function will return a string that will say "Happy Birthday" and whatever the name is. So after the parentheses, type the word 'string' and then open a set of curly brackets.

```golang
func birthday(name string) string {

}
```

Now to return a string along with the value of a parameter, you can concatenate it using the plus sign (+).
So in our case, we will type the keyword `return`, and then the phrase "Happy birthday" in quotations including a space so that we have some space between the words 'birthday' and the person's name, and then the plus sign, and finally the parameter we are using, which is "name".

```golang
func birthday(name string) string {
  return "Happy birthday " + name
}
```

Now, this alone won't do anything. As you know, in Golang, the main package is a special package which is used with the programs that are executable and this package contains the `main()` function. The `main()` function is a special type of function and it is the entry point of the executable programs. It does not take any argument nor return anything.

In order for us to execute this code, we need to put it in the `main()` function. This will print out on to the screen what this 'birthday' function returns. So we will write:

```golang
func main() {
	fmt.Println(birthday("John"))
}
```

If we execute the code, the output should be "Happy birthday John"

### **Example of a function (math)**

We can also write functions to do math for us.
Let's say we want to create a function that will do simple addition.

First we will declare the function by using the keyword `func` and then the name of the function, so let's call it "addThis". The function will take in two parameters, which are numbers that we are going to add together, so we will type:

```golang
func addThis(num1, num2 int)
```

This function will return the sum of these two numbers, so we need to add the return type of an integer and then let's open up the curly brackets.

```golang
func addThis(num1, num2 int) int {

}
```

Inside the body of this function, we want to return the sum of _num1_ and _num2_, so we can type _num1_ and then the plus sign and then _num2_. This will add the two numbers and return the sum.

```golang
func addThis(num1, num2 int) int {
  return num1 + num2
}
```

In order to execute this code, remember we need to add it to the `main()` function, so let's go ahead and do that


```golang
func main() {
  fmt.Println(addThis(3, 6))
}
```

Now when we execute the code, the output should be 9.
