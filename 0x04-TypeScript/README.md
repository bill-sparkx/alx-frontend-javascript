TypeScript Overview

Table of Contents

Introduction to TypeScript
Advantages and Disadvantages of TypeScript
Basic Types in TypeScript
TypeScript Variables
TypeScript Functions
TypeScript Objects
Generics in TypeScript
Interfaces in TypeScript
Benefits of Interfaces
Types of Interfaces
Introduction to TypeScript

TypeScript is a statically typed superset of JavaScript developed and maintained by Microsoft. It adds optional static types, classes, and interfaces to JavaScript, enabling developers to write more robust and maintainable code.

Advantages and Disadvantages of TypeScript

Advantages

Static Typing: Helps in catching errors early during development.
Improved IDE Support: Enhanced autocompletion, navigation, and refactoring.
Enhanced Code Readability and Maintainability: Explicit types make the code more understandable.
Compatibility with JavaScript: TypeScript code transpiles to plain JavaScript, ensuring compatibility with existing projects.
Modern JavaScript Features: Access to the latest ECMAScript features before they are widely adopted in JavaScript.
Disadvantages

Learning Curve: Requires learning new concepts if you're familiar only with JavaScript.
Additional Compilation Step: Code must be compiled, which adds a step to the development process.
Verbose Code: Can be more verbose than JavaScript due to explicit type annotations.
Basic Types in TypeScript

TypeScript provides several basic types to describe the types of values:

boolean: true or false values.
number: numeric values.
string: textual data.
array: arrays of values.
tuple: arrays with a fixed number of elements of specified types.
enum: a way of giving more friendly names to sets of numeric values.
any: any type of value (used to opt-out of type checking).
void: absence of any type (commonly used as a return type).
null and undefined: null and undefined values.
never: represents values that never occur.
Examples

let isDone: boolean = true;
let decimal: number = 6;
let color: string = "blue";
let list: number[] = [1, 2, 3];
let x: [string, number] = ["hello", 10];
enum Color {Red, Green, Blue}
let c: Color = Color.Green;
let notSure: any = 4;
TypeScript Variables

Variables in TypeScript are defined using let, const, or var. TypeScript infers types if not explicitly defined.

Examples

let isComplete: boolean = false;
const pi: number = 3.14;
var name: string = "John";

// Type inference
let age = 25; // inferred as number
TypeScript Functions

Functions in TypeScript can have their parameters and return types explicitly declared. Optional and default parameters are supported.

Examples

function add(x: number, y: number): number {
  return x + y;
}

function greet(name: string, greeting: string = "Hello"): string {
  return `${greeting}, ${name}`;
}

function log(message: string): void {
  console.log(message);
}
TypeScript Objects

Objects in TypeScript can be typed using interfaces or type aliases, ensuring that they have the required structure.

Examples

interface Person {
  name: string;
  age: number;
  location: string;
}

const john: Person = {
  name: "John Doe",
  age: 30,
  location: "New York"
};
Generics in TypeScript

Generics provide a way to create reusable components that work with any type while maintaining type safety.

Examples

function identity<T>(arg: T): T {
  return arg;
}

let output1 = identity<string>("myString");
let output2 = identity<number>(42);
Interfaces in TypeScript

Interfaces define the structure of an object, specifying the types of its properties and methods.

Benefits of Interfaces

Type Checking: Ensures objects adhere to a specific structure.
Code Readability: Makes the code more readable and maintainable.
Reusability: Interfaces can be reused across different parts of an application.
Types of Interfaces

Basic Interface:

interface Vehicle {
  make: string;
  model: string;
  year: number;
}

const car: Vehicle = {
  make: "Toyota",
  model: "Camry",
  year: 2020,
};
Optional Properties:

interface House {
  address: string;
  numberOfRooms?: number; // Optional property
}

const myHouse: House = {
  address: "123 Main St",
};
Read-Only Properties:

interface User {
  readonly id: number;
  name: string;
}

const user: User = {
  id: 1,
  name: "Alice"
};

// user.id = 2; // Error: Cannot assign to 'id' because it is a read-only property.
Function Types:

interface SearchFunc {
  (source: string, subString: string): boolean;
}

const mySearch: SearchFunc = function(src: string, sub: string): boolean {
  return src.search(sub) > -1;
};
Extending Interfaces:

interface Shape {
  color: string;
}

interface Square extends Shape {
  sideLength: number;
}

const square: Square = {
  color: "blue",
  sideLength: 10,
};
Hybrid Types:

interface Counter {
  (start: number): string;
  interval: number;
  reset(): void;
}

function getCounter(): Counter {
  let counter = <Counter>function (start: number) { /* ... */ };
  counter.interval = 123;
  counter.reset = function () { /* ... */ };
  return counter;
}

let c = getCounter();
c(10);
c.reset();
c.interval = 5.0;
This README.md file provides an overview of TypeScript, its advantages and disadvantages, and detailed explanations with examples for basic types, variables, functions, objects, generics, and interfaces.
