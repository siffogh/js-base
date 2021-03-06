# Function Declarations, Function Expressions


## Definitions

### Function Declaration
- if the _function_ is an _LHS_ .
- in other words, if the _function_ keyword is the first thing that appears in the statement.

#### eg:-

```js

  function sum (a, b) {
    return a + b;
  }

```

### Function Expressions
- Every function statement that is not a function declaration.   

#### eg:-
- Assigning a function to a variable:  

```js

  var sum = function (a, b) {
    return a + b;
  }

```

- ES6 Arrow Functions:
```js
  const sum = (a,b) => {
    return a + b;
  }
```
- Inside an _IIFE_ (immediately invoked function expression):
```js
  (
    function sum (a, b) {
      return a + b;
    }
  )(2,3)
```

### Why talking about function declarations and expressions now ?

<img src="https://github.com/siffogh/seif-gifs/raw/master/confused.gif" style="max-height:200px"/>

Well, for two reasons:
1. **It's important to understand function declarations and expressions** before talking about hoisting.
2. It's a confusing topic for some people (at least it was for me).
