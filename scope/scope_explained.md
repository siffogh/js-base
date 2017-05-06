# Scope explained

When the _Engine_ resolves an _LHS_ or _RHS_, the first question that he needs to resolve is: <br> **What is the scope of my _LHS/RHS_ ?** 🤔 In other words, where does my _LHS/RHS_ variable live and can be referred to.

- **Scope**: a space in the code where a _LHS/RHS_ can be referred to. You can think of scope as a bubble where a variable lives.

<img src="https://github.com/siffogh/seif-gifs/raw/master/giphy-downsized.gif"/>

## Example of scope resolution

```js
var x = 10;

function foo () {
  var y = 10;
}

function boo (z) {
  var a;
  a = z + 2;
  m = 10;
}
```

## Compilation: looking for Declarations
- declaration of variable x - Global Scope.
- declaration of function foo - Global Scope.
- declaration of var y - foo scope.
- declaration of function boo - Global Scope.
- declaration of var z - boo scope.
- declaration of var a - boo scope.
- compiler looks for LHS a and finds it.
- compiler looks for LHS m in boo scope but doesn't find so it. Then, the compiler does a lookup for m in the global scope and doesn't find it. If we are not in strict mode, the compiler declares m in global scope. If we are in strict mode, the compiler throws an exception.

## Execution
> **Notice**  <br>
We don't look for declarations anymore.

- assign 10 to var x in global scope.
- assign 10 to var y in foo scope.
- assign z + 2 to a in boo scope.
