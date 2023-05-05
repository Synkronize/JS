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
Also note that some variable names that you may choose can't be used as they are reserved for something else in the language. Like "break" but its okay you don't have to remember the list of words.
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
		- ```javascript
		  function test() {
			if (true) {
				var x = 5;
			}
				console.log(x);
		  }
		  ```
			- So in this example, even though "var x" was declared inside the scope (brackets) of the if statement, then it will still exist even when the if statment ends, it will be destroyed when the function finishes. While if we used the "let x" then the variable would be destroyed as soon as the if statement ends.
- let 
	- same as var but the scope of the variable is tied to the scope it was created in, while the scope for a var is the entire function.
- const
	- When you create a const variable it MUST be initialized, you'll get an error if you don't. A const variable cannot be reassigned. But you can still use it to assign values to other variables.
	- ```javascript
	  const x; // ILLEGAL! it needs to be defined when you create it if its constant!!!
	  const y = 5; // all good :)
	  const y = 10; // ILLEGAL! It's already sent to 5 it cannot be changed (semantics note: when things cant be changed they are called "immutable", the opposite would be called "mutable")
	  const z = y // this is ok we aren't changing Y's value.
	  ```
### Whats happening under the hood?
when we say ` let ten` what is happening? The explanation im giving is very simplified but its the gist of it. When programs run, they run in the memory (RAM) of the computer. Thats where they live their life. When you create the variable x, a space in memory is allocated to that variable and placed in that space of memory is the value 10. This is like  walking down the street and looking at a house #. When you say the address of a house is 42 Wallaby Way, the 42 is the "value" in that address. Although this explanation is not taking into account things like pointers and references. But we will get to that in the OOP section.

## Control flow
So code usually runs top to bottom. To make it branch and make the flow more flexible we use if statements and loops. 
### Conditionals
`if(condition)` keep in mind, 0 is also equivalent to false, and 1 is equivalent to true, also `undefined` evaluates to false. So you can check if a variable exists/has a value by saying `if(!value)` "!" means negate / not, so this would read "if value is **not undefined** (it is defined)"

Say you have a condition fail, and want to trigger another condition check if the first one fails. This is possible using `else if(condition)` you can chain as many else's as you want. The last else will be just `else` and not `else if`

```javascript
	if(isHappy) {}
	else if(isSad) {}
	else if(isSleepy) {}
	else {
		
	}
```
Keep in mind if the first `if` statement is true, then none of the other `else statements` will run. So its one or the other. Same case with `else if` if it succeeds then, the rest of the `else if` checks or `else` checks will not execute. 
### Switch
There is also the `switch(value)` statement you can use this if you don't want to write a bunch of `else if`. It will try to match the value that was given to the switch with a ` case (value)` .



```javascript
	switch(favoriteColor) {
		case "red":
		case "blue":
			doSomething();
		case "green:"
			doSomething2();
		default:
			doSomething3();
	}
	
```

In this example, if the user passes in "blue" to the switch statement, then `case "blue"` will execute the code it contains. But also it `case "green"` and `default` will run their code too! How do we prevent this? you use the `break` command to stop this behavior.

```javascript
	switch(favoriteColor) {
		case "red":
			break;
		case "blue":
			doSomething();
			break;
		case "green:"
			doSomething2();
			break;
		default:
			doSomething3();
	}
```
So here the only code that would run is the code under `case "blue"` because "blue" was passsed in, and the `break` command will basically stop the switch statement from executing any case that comes after `case "blue"`	
### Loops
There are 5 types of loops you'll probably use. Also if you're ever tired of typing `i = i+1`  you can use `i += 1` they mean the same thing, there is also `*=` (multiplication) `/=` (division) `+=` (add) `-` (subtract) `%=` (modulous) 
- for loops
	- has a structure `for(let i = 0; i < 10; i = i + 1)` I like to remember it as starting point, condition to check to see if look keeps going, and what to do at the end of every loop.  Only the first two parts require semicolons. 
	- ```javascript
		for( let i = 0; i < 10; i = i + 1) {
			if(i = 5) {
				break; // say you have a for loop that you dont always want it to run all the way through, you can use break;  to exit the loop.
			}
			else if (i % 2 == 0) (This tests if a number is even) {
				continue; // continue will immediately start the next iteration of the loop. So the continue command is explicitly stating "end of current iteration, go next"
			}
		}
	 ``` 
- while loops
	- basically just keeps running a loop while the condition is true.
	- ```javascript
	  while(petIsHungry) {
		feedPet();
	  } 
	
	  ```
	- **IMPORTANT** when you create a while loop, always think about how to prevent a infinite loop first. As the while loop will check the condition on every loop so within the loop you will need to have code that either escapes the loop by making the condition of the while loop become false, or by using the `break;` statement.
- do..while loops
	- I rarely use this loop, but this loop is the same as the while loop, but the main difference is the loop will run atleast 1 time, and the condition is checked everytime at the end of the loop before it starts again.
	- ```javascript
		do {
			feedPet();
		} while(petIsHungry);
	 ```
	- Same important warning as above, but make sure to keep in mind that the condition is checked at the end. 
- .forEach() loops
	- this one will be explained later.
- for x in z loops
	- also explained later

Keep in mind with the `break` command, that if you have nested loops it will  work only on its nearest loop. If it is in the inner-most loop then using `break;` will cancel the innermost loop. The parent loop of that loop will still run. But if you use `break;` on the parent loop then the parent loop will stop and that also means the child loop will not run. While the `continue` command will move you to the next iteration of your loop, its useful for when you found something you're looking for and don't care about the rest of your loop code, just go to the next iteration of the loop to continue looking for more. 


## Functions
When we execute a function its usually called "calling" I've never heard other terms but the book says "invoking" and also "applying" .
Functions are pretty much a bunch of statements wrapped up in a bundle and then given a name. A function "does" something. A function can give you back something, but that depends on what you're trying to do (see above when I talked about the "void" type). If you like math comparisons, functions are similar to math functions like: f(x) = x + 5 etc, the function takes in x, and returns one value, that value is x + 5. A function cannot return more than 1 value, its true, but misleading,  1 value can mean many things. This will be explained with Arrays and what not. 
The variables that a function can accept are called parameters (also can be called arguments). ` petCat(name, catLocation, whereToPetCat)` Here `name`, `catLocation`, and `whereToPetCat` are parameters. These are what the function expects to receive, of course Javascript has no typing so this looks ambiguous! How is some one suppose to know what type of data the variables are expecting? In typescript: `petCat(name: string, catLocation: string, whereToPetCat: string)` now its easier to see what this function expects when you want to use it.

You can also use functions that produce values as expressions, say you have `isPetCute(petName)` and it returns true or false then you can say `if(isPetCute(petName))` and the if statement will react according to whatever value the `isPetCute` function returns. You can also do:
```javascript
	let x = isPetCute("Curie"); // so this returns true meaning x = true
	//although that is different from this:
	let y = isPetCute; // You are now saying y contains the isPetCute function which means you can do...
	let z = y("Curie"); // this would return true, meaning z = true. 
```
When to use functions:
- Always to be honest
- Try to use functions as much as possible, if you're coding in a function and you've got like 30 lines of code (dosen't have to be 30 what ever you think makes your code look prettier and organized), you should probably make a function to put some of those lines of code in.
- Say you have a bunch of items to process, then you should create a function whose job is to process those items. 
	- This sounds similar to a loop but the difference is that for a function, you are building something that will manipulate data/do things for you so you don't have to keep writing the same code over and over. 
		- a LOOP is for when you want to to go through many elements, if you have a bunch of items like in an array of: `[1,2,3,4,5,6,7,8,9,10]` and say you want to check every element in that array and determine if they are even or odd.  I'll show you first a bad example, then a better example, then a way better example on doing this.
		-	```javascript
			let arr = [1,2,3,4,5,6,7,8,9,10];
			if(arr[0] % 2 === 0){ // % means modulous, modulous gives you back the remainder of a divison. So 4/2 = 2, 4 % 2 = 0 (because there is no remainder, 2 divides 4 evenly, thus 4 % 2 = 0)
								  // this is how you can check if numbers are even or odd.
				console.log(true);
			}
			else {

				console.log(false);
			}
			.... //skipping because im not going to type them all one by 1 lol.
			....

			if(arr[9] % 2 === 0 ){
				console.log(true);
			}
			else {
				console.log(false);
			}
			```
			Imagine if I typed that if statement 10 times, that would be so redundant and a huge waste of time! What if you had 100 numbers to check, or even 1000??? All of our data in the array is of the same type, so they all will behave the same way. This means its perfect to use a function here, to automate it for us.

			Here is a slightly better version.

		-	```javascript
			isEven(num) {
				if(num % 2 === 0) {
					return True;
				} 
				else {// protip: you don't have to put else here, because the "return" statement will exit the function.
					  // if the number is Even the function will exit and return true, there is no need to put an else statement because we would never get to it.
					  // If the number is odd then the if statement will be skipped, and we can simply return false. You don't need an else statement because, if the condition is true in this case
					  // the function will exit this making whatever comes after, irrelevant. Hope that makes sense. 
					return false;
				}
			}

			// Now lets use our function to make this job easier.

			let arr = [1,2,3,4,5,6,7,8,9,10];
			console.log(isEven(arr[0])); // console.log will log whatever the isEven function returns.
			console.log(isEven(arr[1]));
			console.log(isEven(arr[2]));
			console.log(isEven(arr[3]));
			console.log(isEven(arr[4]));
			console.log(isEven(arr[5]));
			console.log(isEven(arr[6]));
			console.log(isEven(arr[7]));
			console.log(isEven(arr[8]));
			console.log(isEven(arr[9]));
			```
			Isnt this code much cleaner than our first example? Although we could still do better here, lets try one more time using our best friend: loop. This time for the sake of saving my fingertips I won't rewrite the array and the `isEven` function just know that they are the same as the above examples.

		-	```javascript
			for(let i = 0; i < 10; i++) {
				console.log(isEven(num));
			}
			```

			and we're done, see how much the code shrunk?? Awesome stuff!   
Remember functions are for automating repetitive work, and loops are for automatically going through lists, or anything that can be iterated through.
Oh and also remember sicne Javascript is a functional language, functions can be passed in/used anywhere just like do with variables. 


# Classes and Objects
This is one of the most important concepts of programming, and it is what makes some languages "Object Oriented".

## What is a class?
A class is like the blueprint or framework of some type of concept or thing you are trying to represent in code.
Im skimming through some of this but it will help to research how classes work. 
For example, lets use a car as an example.

Every car has what?
- make
- model
- year
- moving
- on
- The **ABILITY** to move
- The **ABILITY**  to brake
- The **ABILITY**  to turn on and off.
of course cars have much more to them than this, but this is sufficient for our example.

With this blueprint you can make as many cars as you want, every car will have these properties. 
`make`, `model`, `year`, `moving`, and `on` are all just data these would be called properties/attributues/fields of the class, all of 3 of those words are appropriate.


Now moving, braking, and turning on and off are things the car can **DO**. These are called methods. Methods are just another name for functions, they are called methods because they belong to the class CAR, only the CAR class can use these methods. Methods can also return values just like functions.

What does this look like in code? For this example im going to use Typescript because im more use to that and it should still be readable, some of the syntax may be slightly different in JS but thats just a quick google away.

Also note that a class effectively becomes a type that you can use

```typescript
	class Car {
		make: string;
		model: string;
		year: number;
		moving: bool; // you can also do moving: bool = false so you don't have to set it in the constructor. 
		on: bool;
		constructor(make: string, model: string, year: number){
			this.make = make;
			this.model = model;
			this.year = year;
			this.moving = false;
			this.on = false;
		}
		move(): void {
			this.moving = true;
		}
		brake(): void {
			this.moving = false;
		}
		turnOn(): void {
			this.on = true;
		}
		turnOff(): void {
			this.on = False;
		}
		
	}
```
Also note that a class effectively becomes a type that you can use

Say you had another class called `Stickers` and you wanted to use that class in your `class Car`

You could have a proporty that would be like (in typescript)
`sticker: Sticker`

or another example, you can define that a variable will be of type `Car`: `thisIsACar: Car = new Car();
### what the heck does "this" mean?
"this" refers to the instance of the object itself. Notice how  in the constructor, I use `this.make = make` one of the reasons we use this is because `make = make` makes 0 sense, how do we know what make we're talking about? The one that was passed in? Or the one that belongs to the object? "this" refers to the object itself. Its like saying "yourself" or "me" or "my".

## Objects
Notice how above in the class definition we have the `constructor` function. This function does exactly what it says, it constructs a car object. How do we call the constructor?
Now that we know what a Class definition looks like how do we create Cars?
```typescript
	let car = new Car('Honda', 'Civic', '2000'); // this is called instantiating an object. You have created an "instance" of an object
```

Each object you create (so if u made multiple Cars) have their own independent versions of their properties. One car can be off, and another can be on after all, just like real life. 


You can also have multiple constructors, this is called overloading so you can create different constructors that createa  car object using different types of data passed in if the constructor above is not sufficient.

We can access the properties of a car object by using `.`.

```typescript
console.log(car.make);
console.log(car.moving); //moving would be false here due to the constructor.
car.move();
console.log(car.moving); // moving would be true here due to the move method.

```

Theres more to objects but this is the basics.

### Quick note about Objects
Remember the section above about whats happening under the hood? It helps to know whats happening under the hood for objects.

When you do `let car = new Car('Honda', 'Civic', '2000');` The object is instantiated. Unlike primitive variables (basic numbers, basic strings, basic booleans) the car variable does not contain the object. The Object is created in a random spot of memory in the computer and the variable ***POINTS*** to that spot in memory.  Thats kinda why you use `car.on` `car` tells the computer where the object is, and `.on()` is actually accessing that method. 
This means if you have two objects `car` and `car2` and you say `car = car2` you are ***NOT*** copying `car2` into `car` (unless you overload the operator google that one its wild). Whats actually happening is you are saying the `car` variable no longer points to what ever `car` was pointing at. It now points to whatever `car2` points at. This means that `car` and `car2` have the same ***EXACT*** value, they both point to 1 object in memory.

This is useful tot hink about when working on the LinkedList problems below.
### Static property

say we added an extra property to our car class called:

```typscript
static recall: boolean;
```
static means that the variable is tied to the class ***NOT*** the instance of the Object.  This means that every object you create shares only 1 version of this variable. 
If `recall = true` then every Car object you instantiate would have recall = true as their property.
## Inheritance
We have a car class, but a car class is too vague, we have SUV's, Trucks, Sedans, etc. These are all cars but are different types. They all share the same characteristics of `Car` but also do more. 

You can extend classes to create subclasses by doing: 

```typescript
	class SUV extends Car {
		
	}
```

Honestly, this page explains it better than I can but let me know if you have questions 
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes
Make sure to understand super(). Internet will explain that better than I could, but also lmk if you have questions about it.


### private/public/protected
you may see variables labeld private, protected, public not sure if Javascript uses all of these but in various programming languages you learn, you may see these.

- private: 
	- if a variable/function is marked private, then you cannot use `.` to access the value of the variable or function. If `on` was private then you could not say `Car.on`, this helps make sure that you don't assign the `on` variable to some weird value that is unexpected in your code. It is good coding practice to use private when needed. You can set or get the properties of the object by adding getters and setter methods in the class definition.
	- Also the variable can only be used in it's class and not any subclasses if marked as private
```typescript
	getOn(): boolean {
		return this.on;
	}
	setOn(on: boolean): void {
		this.on = on;
	}
```
- protected
	- same as private but subclasses have access.
- public
	- is the default, the access is open and not restricted.
	
### Polymorphism
Useful concept to know this basically means that if you have a subclass then anywhere that the parent class is used, you can use the subclass instead, because every SUV is a Car, but not every Car is an SUV get it?  I think when you do this though, the subclass will get converted into its parent class so I don't think you can use the subclasses methods/properties but I may be wrong on this!


# Certain things are already classes/objects in Javascript
In Javascript Arrays are already classes `let arr = [1,2,3]` is an object and thus has useful methods that you can access.  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach

This is where .forEach comes into play
You can do `arr.forEach(() => {});` to loop through each element in the array, the argument that forEach acceepts is a function (proper term is "***callback***" function). This basically means that when u use `.forEach` you can pass in a function that will do whatver you want with each value in the array.

Example:

```javascript
let arr = [1,2,3]
arr.forEach((number) => { // what ever element of the array that forEach is on will be passed in as the first parameter to the function that you pass into forEach.
	if(number % 2 === 0) {
		console.log(true);
	}
	else {
		console.log(false);
	}
});

// or say I take the isEven function from previous example.

arr.forEach(isEven(number)); is also valid.
```
Keep in mind .forEach iterates over the array, you cannot change the array in the `.forEach` function because that would mess up the structure. You'll get an error. You can copy the array and then make changes if you want to do something like that. Also `.forEach` cannot be cancelled (if you already found/finished what you needed) instead you can use `.some()` instead https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some
`.some()` will stop looping once the callback function **returns** a truthy value (boolean, or 1 I guess or anything else that would evaluate to true).

# Challenge problems
I think with above information you should be able to take on these problems below these challenges will build your coding fundamentals, and may be useful sometimes. 

1. Using an array [1,2,3,4,5,6] use a loop to create a copy of this array. Store the copy in another variable, without using `.push()` You can also this problem again and use `.push()` and other methods
2. With the same array above, use a loop to reverse the array.
3. Make an array that is not sorted, think about the simpelest way you can sort the array so that the numbers are in order. Use a loop to do this, you can look up some simple sorting algorithms like bubblesort and insertion sort, but try to really understand what they are doing.
4. Make two arrays and use a loops to join them.
5. Make an array with duplicates and remove the duplicates.

# Linked List Problems
A Linked List is similar to an array but it works completely different, but I think in most modern languages arrays are linked lists or atleast modified ones.

Try to visualize this image:
You're at a railroad crossing and you see the train going by. The train has multiple carts, all the carts are connected but they are open (so you can look inside of them while you're waiting at the railroad crossing). This is an array, you can go directly to any spot in an array ex: `arr[1] arr[9] arr[500]` you can also start from the start of the train and go to the last cart `arr[0]...arr[x]`.

A linked list on the other hand, the carts would be closed you cannot go directly to them. You must start from the front of train and go where ever you need to. So like 1 -> 2 -> 3 -> 4. But the connectors of the train are re-arrangable by just changing what the connectors are connecting (pointing) to. 
You can do 2 -> 3 -> 4 -> 1 by making 4 connect to 1, make 2 the new start of the train (head), and 1 connects to now nothing (it is the end of the train, or the trailer).



Try to think about how you can create a linked list using Classes and their methods.
You shouldnt need an array to create a Linked List, but your data could be an array if you want. Make the data whatever you want (I reccomend numbers or strings to make it easier)

I'll give you a hint you'll want a class called LinkedList and a separate class called Node  (or whatever you want to name them). Node would be each cart, while LinkedList represents the whole LinkedList structure as a whole.

A Linked List has:
A `head` (start), a `trailer` (end),  and if you want you can also give it a `size` variable that will help with conditions.

A Node has:
`data`, and a `next` property (hint: what type would next be? It's gotta be an OBJECT not a primitive type like int, etc, with that in mind and thinking of how a linked list would work, what kind of object would `next` be?)


Try to think about what methods each classes would have and what they would look like.

The code is readily availaible online but if you don't want to immediately see the answer just ask me and I'll try to give a hint, you'll have to send the code over tho.

while loops are very useful here, and you'll want to make sure to check for undefined.

After you can create a basic linked list, up the difficulty by trying to create a circular linked list.
that would look like: 1 -> 2 -> 3 -> 4 -> 1 (loops back to the start)


You can then up the difficulty again, by making  a doubly linked list 
that means you can travel in both directions. Think about how your classes may change!
1 -> 2 -> 3 -> 4 
1 <-  2 <-  3 <-4  (this is not two list, this is signifying that they can connect forward and connect backwards)


Make sure to think about how connecting and disconnecting works depending on where you are in the list (front, middle, end)


If after this you're really thirsting for knowledge and fun and more of a challenge. Then I would reccomend looking up binary trees, but you'll have to understand recursion, and understand what inorder, post order, and preorder traversal is. 
Heres a good video on recursion: https://www.youtube.com/watch?v=LteNqj4DFD8 (actually idk if its good, its the first thing on utube LOL)