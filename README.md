# JavaScript Knowledge Base



## Scope


There's 2 kinds of scopes:
- **Lexical Scope** (in other words, the scope decided by the author).
- **Dynamic Scopre** (in the case of _this_ keyword).


### Lexical Scope

#### Units of Scope
- Before _ES6_, the smalled unit of scope was a function.
- Now with _let_ and _const_, the smallest unit of scope is a block.

#### Order of Execution
- The code is compiled first and the declarations are resolved.
- This leads to Hoisting: the function declarations are pulled to the topmost order of execution, then the variable declarations, and finally the other expressions.
- The code is then executed.

#### LHS and RHS
- An expression can be either a **LHS** (Left Hand Side) or **RHS**.

- **LHS**: if it is at the left side of an assignment.
- **RHS**: anything that is not a **LHS**.


eg:-

```js
var x = 12;

function sayHello () {

	console.log("Hello !");
}

var sayBye = function () {
	console.log("Bye !");
}

```

LHS: x, sayBye.  
RHS: sayHello.


#### How is the lexical scope determined ?

- It's a buttom-up process: does the variable exist in the current scope ? If not check the outer scope.
- in the case of LHS, we are in non-strict mode and the variable does not exist, it is automatically created.
