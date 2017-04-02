## Scope

### Scope and the JavaScript Compiler
### Important Concepts

#### Scope:
Where to look for things.

#### What are we looking for?
Variables (including functions).

#### Who is looking for variables?
The JS compiler.

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