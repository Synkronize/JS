# Introduction
For Javascript I'm going to use this book its free here on its official site: https://eloquentjavascript.net/. I've always used this book, as kind of my reference when it comes to Javascript so I find it pretty useful.
This is probably going to start off chaotic but hopefully gets better as we go on. So let me know if you have a question on **anything**. I'm going to start from the basics. But tbh we're going to use Typescript as it makes working with Javascript a lot easier, and it dosen't require much time to pick up. It pretty much is kinda of like Javascript 2.0. It's main thing is it lets you give variables a type in Javascript because namely. This helps with fixing errors because Javascript normally does not have typing so when it spits out errors they're so ambiguous. ITS THE WORST.
# What is Javascript?
Javascript (no relation to Java) is a very popular programming language for building web applications. It's used a lot there, but Node.js also exists to give an environment for Javascript to be able to run outside of the browser. 
## Javascript is an Object Oriented Programmming Language (OOP)
### What is an Object Oriented Language?
The best way I can explain this is that, when I learned coding my first language was C which was created in 1973. So C is a procedural language, as I was taught  but im sure there are many small changes and updates to it since then that allows it to be closer to an OOP. But as I learned it, it was strictually procedural. Procedural just means that the code runs in line order.  For example in C say I wrote a small function that adds numbers and then divide the sum and checks that the divisor is not 0:
```C
void doSomething() { 
// "void" stands for a return type, in languages that have variable typing then your function can also have a type. 
// you specify a type then the function MUST return (give-back, when its done running)
// a value that matches the type it was defined with.  
// This function has type "void" so it returns nothing, and will not need a return statement.
// int is a variable type, here I am specifying that the variable "a" is an integer and that what we expect it to hold is a number. 
	int a;
	int b;
	int finalValue;
	// small note, I was taught that it helps to remember the "=" sign when assigning as meaning "gets"
	// a gets 5, b gets 2
	// double equal == is the actual equal sign.
	a = 5;
	b = 2;
	finalValue = a + b;
	if (b != 0) {
		// I forget if C has the shorthand.
		// But you can also do finalValue /= b (works with others like +, *, etc)
		finalValue = finalValue / b
	}	
	
}
```
So here the code in this function will run from the first line (int a) all the way to the end of the function. This is procedural code, I'm pretty sure for the most part every language behaves like this when you're coding as code runes line-by-line usually. But the difference is that this procedural languages (usually the older ones) only ran this way (don't quote me on that lol). But in Javascript if you wrote the same code it would also be procedural:
```javascript
function doSomething() {
	let a;
	let b;
	let finalValue;
	a = 5;
	b = 2;
	finalValue = a + b;
	if (b !== 0) {
		finalValue /= b;
	}
}
```

and in TypeScript:

```typescript
// I'll make this one return a value just to show the typing of the function since TypeScript has typing.
doSomething(): number {
	let a: number;
	let b: number;
	let finalValue: number;
	finalValue = a + b;
	if (b !== 0) {
		finalValue /= b;
	}
	return finalValue
}

```

All three of these examples do the same thing and all are procedural code snippets. Procedural code can be pretty hard to work with which is why we have OOP, OOP is basically instead focusing on coding using objects, that have properties and their own set of functions then we can code them in a more natural way. It's kind of hard to explain it'll make more sense when we get there. For now just picture that you could have a "Bearded Dragon object"
It would be able to have properties in it like color, sex, personality etc.  Also have its  own functions like, "fightWaterKy (or is it Kai?), eatFood(), etc. OOP helps us build things by letting us think of them as real world physical things.

## Javascript is also a functional programing language
https://www.telerik.com/blogs/functional-programming-javascript#:~:text=Functions%20in%20JavaScript%20are%20first,the%20same%20way%20as%20variables.&text=Functions%20in%20JavaScript%20are%20objects,back%20to%20their%20constructor%20function.
Honestly this article can explain it better than I can, its kinda something you end up just doing. I've never had some one ask me to "functional program something".  Let me know if you have any questions!
# Program Structure
A line of code is called a statement, what the statement contains is usually called an expression.  So like "words" (expression) in a "sentence" (statement).
## Binding values
I was taught special wording, for binding values so maybe it could help. When you create a variable but don't give it a value (like the variable here "five") that is called "declaring". When you create a variable and give it a value, it is called "initializing" (But I guess you also decalred it?). All semantics though, binding, assigning, and initializing are all pretty much the same thing.

```javascript
let five;
let ten = 10;
```
and for typescript
```typescript
let five: number;
let ten: number = 10;
```
There is also "var" along with "let" and "const"
- var
	- not really used any more and is nearly the same as "let"
		- the difference is that a variable defined with "let" will only exist in the scope that is part of, while var are availiable throughout the function that they were declared in.
		- ```
		  function test() {
			if (true) {
					var x = 5;
				}
				console.log(x)
		  }
		  ```
			- So in this example, even though "var x" was declared inside the scope (brackets) of the if statement, then it will still exist even when the if statment ends, it will be destroyed when the function finishes. While if we used the "let x" then the variable would be destroyed as soon as the if statement ends.




