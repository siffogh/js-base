# JavaScript Knowledge Base

## TODO
- [ ] Scope

	- [x] Scope and the JavaScript Compiler
	- [x] Compiling Function Scope
	- [ ] Execution of Function Code
	- [ ] Scope and Execution Example
	- [ ] Function Declarations, Function Expressions, and Block Scope
	- [ ] Lexical Scope
	- [ ] Cheating Lexical Scope: eval
	- [ ] IIFE Pattern
	- [ ] Block Scope in ES6
	- [ ] Dynamic Scope
	- [ ] Hoisting
	- [ ] this Keyword
	- [ ] Binding Confusion
	- [ ] Explicit Binding
	- [ ] The New keyword

- [ ] Closures

	- [ ] Closures explained
	- [ ] Closure Examples
	- [ ] Module Patterns

- [ ] Object Orienting

	- [ ] Prototype
	- [ ] Prototypes Explained
	- [ ] Prototype Linkages
	- [ ] Prototype: Objects Linked
	- [ ] Linked Prototype Diagram
	- [ ] Inheritance
	- [ ] OLOO

- [ ] Async Patterns

	- [ ] Callbacks
	- [ ] Solving Callback Problems
	- [ ] Generators
	- [ ] Promises
	- [ ] asynquence

## Scope

### Scope and the JavaScript Compiler
### Important Concepts

#### Scope:
Where to look for things.

#### What are we looking for?
Variables (including functions).

#### Who is looking for variables?
The JS compiler.

#### Is JavaScript a compiled language?
JavaScript is a compiled language. Though, it's not the same as how other languages (like C++, Java ... ) are compiled. It's not compiled into byte code or binary, the original source code is kept.
It is not an **interpreted** language. An interpreted language is interpreted and executed line by line. However, in a compiled language, the compiler does an initial pass through the code and then one or more passes before executing it.

### Some compiler terminology
- ** LHS (Left Hand Side):** left hand side of an assignment.
- ** RHS (You guess ...):** Any expression that is not an assignment.  
eg:-  
```js
var x = 10;  // LHS: x, RHS: 10
var y = x; // LHS: y, RHS: x
function foo (z) {} // LHS: foo, z
```

### Compiling Function Scope

```js
var x = 10;

function foo () {
  var y = 10;
}

function boo (z) {
  var a = z + 2;
}
```

#### Compilation: looking for Declarations
- declaration of var x - Global Scope.
- declaration of function foo - Global Scope.
- declaration of var y - foo scope.
- declaration of function boo - Global Scope.
- declaration of var z - boo scope.
- declaration of var a - boo scope.

#### Execution
> We don't look for declarations anymore.

- assign 10 to var x in global scope.
- assign 10 to var y in foo scope.
- assign z + 2 to a in boo scope.

### Execution of Function Code
### Scope and Execution Example
### Function Declarations, Function Expressions, and Block Scope
### Lexical Scope
### Cheating Lexical Scope: eval
### IIFE Pattern
### Block Scope in ES6
### Dynamic Scope
### Hoisting
### this Keyword
### Binding Confusion
### Explicit Binding
### The New keyword

## Closures

### Closures Explained
### Closure Examples
### Module Patterns

## Object Orienting

### Prototype
### Prototypes Explained
### Prototype Linkages
### Prototype: Objects Linked
### Linked Prototype Diagram
### Inheritance
### OLOO

## Async Patterns

### Callbacks
### Solving Callback Problems
### Generators
### Promises
### asynquence
