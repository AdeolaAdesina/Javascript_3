# Javascript Functions and Scope

# What are Functions?

When first learning how to calculate the area of a rectangle, there’s a sequence of steps to calculate the correct answer:

- Measure the width of the rectangle.
- Measure the height of the rectangle.
- Multiply the width and height of the rectangle.

With practice, you can calculate the area of the rectangle without being instructed with these three steps every time.

We can calculate the area of one rectangle with the following code:

```
const width = 10;
const height = 6;
const area =  width * height;
console.log(area); // Output: 60
```

Imagine being asked to calculate the area of three different rectangles:

```
// Area of the first rectangle
const width1 = 10;
const height1 = 6;
const area1 =  width1 * height1;
 
// Area of the second rectangle
const width2 = 4;
const height2 = 9;
const area2 =  width2 * height2;
 
// Area of the third rectangle
const width3 = 10;
const height3 = 10;
const area3 =  width3 * height3;
```


In programming, we often use code to perform a specific task multiple times. 

Instead of rewriting the same code, we can group a block of code together and associate it with one task, then we can reuse that block of code whenever we need to perform the task again. 

We achieve this by creating a function. 

A function is a reusable block of code that groups together a sequence of statements to perform a specific task.

In this lesson, you will learn how to create and use functions, and how they can be used to create clearer and more concise code.


# Function Declarations

In JavaScript, there are many ways to create a function. 

One way to create a function is by using a function declaration. 

Just like how a variable declaration binds a value to a variable name, a function declaration binds a function to a name, or an identifier. Take a look at the anatomy of a function declaration below:


A function declaration consists of:

- The function keyword.
- The name of the function, or its identifier, followed by parentheses.
- A function body, or the block of statements required to perform a specific task, enclosed in the function’s curly brackets, ```{ }```.

We should also be aware of the hoisting feature in JavaScript which allows access to function declarations before they’re defined.

Take a look at example of hoisting:

```
greetWorld(); // Output: Hello, World!
 
function greetWorld() {
  console.log('Hello, World!');
}
```


## Class work

1. Let’s create a function that prints a reminder to the console. Using a function declaration, create a function called getReminder().

2. In the function body of getReminder(), log the following reminder to the console: 'Water the plants.'

3. Let’s create another function that prints a useful Spanish travel phrase to the console.

Using a function declaration, create a function called greetInSpanish().

4. Add code to the function body of greetInSpanish():

In the function body console.log() the following Spanish phrase to the console: 'Buenas tardes.'

Output:

![Screenshot_171](https://user-images.githubusercontent.com/29931071/200910091-3e7964a0-8967-401b-ae76-9a4242aa4f53.png)



# Calling a Function

As we saw in previous exercises, a function declaration binds a function to an identifier.

However, a function declaration does not ask the code inside the function body to run, it just declares the existence of the function. The code inside a function body runs, or executes, only when the function is called.

To call a function in your code, you type the function name followed by parentheses.

![Screenshot_172](https://user-images.githubusercontent.com/29931071/200910691-8b49b9de-949c-4f87-aa1c-b2050cacfa10.png)

This function call executes the function body, or all of the statements between the curly braces in the function declaration.

![Screenshot_173](https://user-images.githubusercontent.com/29931071/200910817-20d8e1cb-4e58-4950-a933-27837ea7800e.png)


We can call the same function as many times as needed.

Let’s practice calling functions in our code.

## Class work

1. Imagine that you manage an online store. When a customer places an order, you send them a thank you note. Let’s create a function to complete this task:

Define a function called sayThanks() as a function declaration.

In the function body of sayThanks(), add code such that the function writes the following thank you message to the console when called: 'Thank you for your purchase! We appreciate your business.'

2. Call sayThanks() to view the thank you message in the console.

3. Functions can be called as many times as you need them.

Imagine that three customers placed an order and you wanted to send each of them a thank you message. Update your code to call sayThanks() three times.

Output:

![Screenshot_174](https://user-images.githubusercontent.com/29931071/200911498-a5cd9b2a-7c7c-4e2c-b3a4-544ead7fbf21.png)


# Parameters and Arguments

So far, the functions we’ve created execute a task without an input. 

However, some functions can take inputs and use the inputs to perform a task. When declaring a function, we can specify its parameters. 

Parameters allow functions to accept input(s) and perform a task using the input(s). We use parameters as placeholders for information that will be passed to the function when it is called.

Let’s observe how to specify parameters in our function declaration:

![Screenshot_175](https://user-images.githubusercontent.com/29931071/200912270-971c27e5-23b9-45ac-8e83-1cd6c05fe5f1.png)


In the diagram above, calculateArea(), computes the area of a rectangle, based on two inputs, width and height. 

The parameters are specified between the parenthesis as width and height, and inside the function body, they act just like regular variables

When calling a function that has parameters, we specify the values in the parentheses that follow the function name. 

The values that are passed to the function when it is called are called arguments.

![Screenshot_176](https://user-images.githubusercontent.com/29931071/200912591-c7651e7b-5b63-4de6-8c4f-f6cfd807ab69.png)


In the function call above, the number 10 is passed as the width and 6 is passed as height. Notice that the order in which arguments are passed and assigned follows the order that the parameters are declared.

![Screenshot_177](https://user-images.githubusercontent.com/29931071/200912855-c251fdd7-27cb-4e22-82ce-86dd9e1c3431.png)

The variables rectWidth and rectHeight are initialized with the values for the height and width of a rectangle before being used in the function call.

## Class work

```
function sayThanks() {
  console.log('Thank you for your purchase! We appreciate your business.');
}
```

1. The sayThanks() function works well, but let’s add the customer’s name in the message.

Add a parameter called name to the function declaration for sayThanks().

2. With name as a parameter, it can be used as a variable in the function body of sayThanks().

Using name and string concatenation, change the thank you message into the following:

```
'Thank you for your purchase '+ name + '! We appreciate your business.'
```

3. A customer named Cole just purchased something from your online store. Call sayThanks() and pass 'Cole' as an argument to send Cole a personalized thank you message.


Output:

![Screenshot_178](https://user-images.githubusercontent.com/29931071/200913974-d6281167-7613-45b0-9836-993fd7cfa262.png)



# Default Parameters

One of the features added in ES6 is the ability to use default parameters. Default parameters allow parameters to have a predetermined value in case there is no argument passed into the function or if the argument is undefined when called.

Take a look at the code snippet below that uses a default parameter:

```
function greeting (name = 'stranger') {
  console.log(`Hello, ${name}!`)
}
 
greeting('Nick') // Output: Hello, Nick!
greeting() // Output: Hello, stranger!
```

## Class work

The function makeShoppingList() creates a shopping list based on the items that are passed to the function as arguments.

Imagine that you always purchase milk, bread, and eggs every time you go shopping for groceries. To make creating a grocery list easier, let’s assign default values to the parameters in makeShoppingList().

Change the parameters of makeShoppingList() into default parameters :

Assign ‘milk’ as the default value of item1.
Assign ‘bread’ as the default value of item2.
Assign ‘eggs’ as the default value of item3.


Output:

![Screenshot_179](https://user-images.githubusercontent.com/29931071/200915376-4479eddd-96d9-499c-9479-98e842d2de08.png)



# Return

When a function is called, the computer will run through the function’s code and evaluate the result of calling the function. By default that resulting value is undefined.

```
function rectangleArea(width, height) {
  let area = width * height;
}
console.log(rectangleArea(5, 7)) // Prints undefined
```

In the code example, we defined our function to calculate the area of a width and height parameter. 

Then rectangleArea() is invoked with the arguments 5 and 7. But when we went to print the results we got undefined. 

Did we write our function wrong? No! In fact, the function worked fine, and the computer did calculate the area as 35, but we didn’t capture it. 

So how can we do that? With the keyword return!

![Screenshot_180](https://user-images.githubusercontent.com/29931071/200915868-44866643-b23d-4c64-822a-8f0daf73d367.png)

To pass back information from the function call, we use a return statement. 

To create a return statement, we use the return keyword followed by the value that we wish to return.

When a return statement is used in a function body, the execution of the function is stopped and the code that follows it will not be executed. Look at the example below:

```
function rectangleArea(width, height) {
  if (width < 0 || height < 0) {
    return 'You need positive integers to calculate area!';
  }
  return width * height;
}
```

The return keyword is powerful because it allows functions to produce an output. We can then save the output to a variable for later use.


## Class work

1. Imagine if we needed to order monitors for everyone in an office and this office is conveniently arranged in a grid shape. We could use a function to help us calculate the number of monitors needed!

Declare a function monitorCount() that has two parameters. The first parameter is rows and the second parameter is columns.

2. Let’s compute the number of monitors by multiplying rows and columns and then returning the value.

In the function body of the function you just wrote, use the return keyword to return rows * columns.

3. Now that the function is defined, we can compute the number of monitors needed. Let’s say that the office has 5 rows and 4 columns.

Declare a variable named numOfMonitors using the const keyword and assign numOfMonitors the value of invoking monitorCount() with the arguments 5 and 4.

4. To check that the function worked properly, log numOfMonitors to the console.

Output:

![Screenshot_181](https://user-images.githubusercontent.com/29931071/200917692-5d7cbba7-1317-4d4f-8fef-b42c93677335.png)


# Helper Functions

We can also use the return value of a function inside another function. These functions being called within another function are often referred to as helper functions. Since each function is carrying out a specific task, it makes our code easier to read and debug if necessary.

If we wanted to define a function that converts the temperature from Celsius to Fahrenheit, we could write two functions like:

```
function monitorCount(rows, columns) {
  return rows * columns;
}

function costOfMonitors(rows, columns) {
  return monitorCount(rows, columns) * 200;
}

const totalCost = costOfMonitors(5, 4)

console.log(totalCost);
```

![Screenshot_182](https://user-images.githubusercontent.com/29931071/200918129-435c7a86-f634-47d3-addb-cb58438ca917.png)



# Function Expressions

Another way to define a function is to use a function expression. To define a function inside an expression, we can use the function keyword. In a function expression, the function name is usually omitted. A function with no name is called an anonymous function. A function expression is often stored in a variable in order to refer to it.

Consider the following function expression:

![Screenshot_183](https://user-images.githubusercontent.com/29931071/200918423-b8eefffe-57d4-4d69-b5f8-ad05e7bb93fc.png)


To declare a function expression:

- Declare a variable to make the variable’s name be the name, or identifier, of your function. Since the release of ES6, it is common practice to use const as the keyword to declare the variable.

- Assign as that variable’s value an anonymous function created by using the function keyword followed by a set of parentheses with possible parameters. Then a set of curly braces that contain the function body.

To invoke a function expression, write the name of the variable in which the function is stored followed by parentheses enclosing any arguments being passed into the function.

- variableName(argument1, argument2)

Unlike function declarations, function expressions are not hoisted so they cannot be called before they are defined.

## Class work

1. Let’s say we have a plant that we need to water once a week on Wednesdays. We could define a function expression to help us check the day of the week and if the plant needs to be watered:

Create a variable named plantNeedsWater using the const variable keyword.
Assign an anonymous function that takes in a parameter of day to plantNeedsWater.

2. Now we need to add some code to the function body of plantNeedsWater():

In the function body add an if conditional that checks day === 'Wednesday'.
If the conditional is truthy, inside the if code block, use the return keyword to return true.

3. On days that aren’t 'Wednesday', plantNeedsWater() should return false:

Add an else statement after the if statement.
Inside the else statement use the return keyword to return false.

4. Call the plantNeedsWater() and pass in 'Tuesday' as an argument.

5. Let’s check that plantNeedsWater() returned the expected value.

Log plantNeedsWater('Tuesday') to the console. If it worked correctly, you should see false logged to the console.

Output:

![Screenshot_184](https://user-images.githubusercontent.com/29931071/200919607-b3ba9750-cd20-450e-a99d-8eec083d0d73.png)


# Arrow Functions

ES6 introduced arrow function syntax, a shorter way to write functions by using the special “fat arrow” () => notation.

Arrow functions remove the need to type out the keyword function every time you need to create a function. 

Instead, you first include the parameters inside the ( ) and then add an arrow => that points to the function body surrounded in { } like this:

```
const rectangleArea = (width, height) => {
  let area = width * height;
  return area;
};
```

## Class work

```
const plantNeedsWater = function(day) {
  if (day === 'Wednesday') {
    return true;
  } else {
    return false;
  }
};
```

Change plantNeedsWater() to use arrow function syntax.

Output:

![Screenshot_185](https://user-images.githubusercontent.com/29931071/200920482-47d28839-931b-4d4a-9c44-0f1329502dd1.png)


# Concise Body Arrow Functions

JavaScript also provides several ways to refactor arrow function syntax. The most condensed form of the function is known as concise body. We’ll explore a few of these techniques below:

1. Functions that take only a single parameter do not need that parameter to be enclosed in parentheses. However, if a function takes zero or multiple parameters, parentheses are required.

![Screenshot_186](https://user-images.githubusercontent.com/29931071/200921967-8c9a2a61-cfcc-46cb-9a7a-95744d3e55b4.png)


2. A function body composed of a single-line block does not need curly braces. Without the curly braces, whatever that line evaluates will be automatically returned. The contents of the block should immediately follow the arrow => and the return keyword can be removed. This is referred to as implicit return.

![Screenshot_187](https://user-images.githubusercontent.com/29931071/200922287-4e8ee028-a870-48ea-a6b7-6f41cffe7f8d.png)


So if we have a function:

```
const squareNum = (num) => {
  return num * num;
};
```
We can refactor the function to:

```
const squareNum = num => num * num;
```

Notice the following changes:

- The parentheses around num have been removed, since it has a single parameter.
- The curly braces { } have been removed since the function consists of a single-line block.
- The return keyword has been removed since the function consists of a single-line block.

## Class work

```
const plantNeedsWater = (day) => {
  return day === 'Wednesday' ? true : false;
};
```
Let’s refactor plantNeedsWater() to be a concise body. Notice that we’ve already converted the if/else statement to a ternary operator to make the code fit on one line.

Output:

![Screenshot_188](https://user-images.githubusercontent.com/29931071/200922777-2bab1051-a69e-4fcb-80b7-b90228932850.png)
