# Introduction
For Javascript I'm going to use this book its free here on its official site: https://eloquentjavascript.net/. I've always used this book, as kind of my reference when it comes to Javascript so I find it pretty useful.
This is probably going to start off chaotic but hopefully gets better as we go on. So let me know if you have a question on **anything**. I'm going to start from the basics. But tbh we're going to use Typescript as it makes working with Javascript a lot easier, and it dosen't require much time to pick up. It pretty much is kinda of like Javascript 2.0. It's main thing is it lets you give variables a type in Javascript because namely. This helps with fixing errors because Javascript normally does not have typing so when it spits out errors they're so ambiguous. ITS THE WORST.
# What is Javascript?
Javascript (no relation to Java) is a very popular programming language for building web applications. It's used a lot there, but Node.js also exists to give an environment for Javascript to be able to run outside of the browser. 
## Javascript is an Object Oriented Programmming Language (OOP)
### What is an Object Oriented Language?
The best way I can explain this is that, when I learned coding my first language was C which was created in 1973. So C is a procedural language, as I was taught  but im sure there are many small changes and updates to it since then that allows it to be closer to an OOP. But as I learned it, it was strictually procedural. Procedural just means that the code runs in line order.  For example in C say I wrote a small function that adds numbers and then divide the sum and checks that the divisor is not 0:
```
void doSomething() { 
// "void" stands for a return type, in languages that have variable typing then your function can also have a type. If you specify a type then the function MUST return (give-back, when its done running) a value that matches the type it was defined with.  This function has type "void" so it returns nothing, and will not need a return statement.
//int is a variable type, here I am specifying that the variable "a" is an integer and that what we expect it to hold is a number.
	int a;
	int b;
	int finalValue;
	a = 5;
	b = 2;
	finalValue = a + b;
	if (b != 0) {
		// I forget if C has the shorthand but you can also do finalValue /= b (works with others like +, *, etc)
		finalValue = finalValue / b
	}	
	
}
```
So here the code in this function will run from the first line (int a) all the way to the end of the function. This is procedural code, I'm pretty sure for the most part every language behaves like this when you're coding as code runes line-by-line usually. But the difference is that this procedural languages (usually the older ones) only ran this way (don't quote me on that lol). But in Javascript if you wrote the same code it would also be procedural:
```
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

```
// i'll make this one return a value just to show the typing of the function since TypeScript has typing.
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

All three of these examples do the same thing and all are procedural code snippets. 


