## Scope
>**Notice** <br> There are two types of scopes: _dynamic scope_ and _lexical/static_ scope.
JSBase will only focus on static/lexical scope.

### Some compiler terminology
- **LHS (Left Hand Side):** left hand side of an assignment.
- **RHS (You guess ...):** Any expression that is not an assignment.  
eg:-  
```js
var x = 10;  // LHS: x, RHS: 10
var y = x; // LHS: y, RHS: x
function foo (z) {} // LHS: foo, z
```

### Scope explained

When the _Engine_ resolves an _LHS_ or _RHS_, the first question that he needs to resolve is: <br> **What is the scope of my _LHS/RHS_ ?** 🤔 In other words, where does my _LHS/RHS_ variable live and can be referred to.

- **Scope**: a space in the code where a _LHS/RHS_ can be referred to. You can think of scope as a bubble where a variable lives.

<img src="https://github.com/siffogh/seif-gifs/raw/master/giphy-downsized.gif"/>

#### Example of scope resolution

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

#### Compilation: looking for Declarations
- declaration of variable x - Global Scope.
- declaration of function foo - Global Scope.
- declaration of var y - foo scope.
- declaration of function boo - Global Scope.
- declaration of var z - boo scope.
- declaration of var a - boo scope.
- compiler looks for LHS a and finds it.
- compiler looks for LHS m in boo scope but doesn't find so it. Then, the compiler does a lookup for m in the global scope and doesn't find it. If we are not in strict mode, the compiler declares m in global scope. If we are in strict mode, the compiler throws an exception.

#### Execution
> **Notice**  <br>
We don't look for declarations anymore.

- assign 10 to var x in global scope.
- assign 10 to var y in foo scope.
- assign z + 2 to a in boo scope.


### Cheating the Scope
> **Notice:** <br>
The 2 workarounds we are going to see are deprecated.

#### with keyword
The _with_ keyword allows to access/modify the values of an object with a simpler syntax. <br>

#### eg:-

Consider the following object:

```js
var person = {
  name: "Bob",
  age: 22,
  job: "software engineer"
}
```
The following two pieces of code modify the properties of _person_ in the same way:

```js
person.name = "James";
person.age = 23;
person.job = "full stack developer";

```

```js
with(person){
  name = "James";
  age = 23;
  job = "full stack developer";
}
```

#### What just happened ?

<img src="https://github.com/siffogh/seif-gifs/raw/master/wow-gif.gif" style="max-height:200px"/>

When executing the body of _with_, the engine does the following:
- creates a specific scope attached to the body of person.
- when assigning/accessing any property, it looks for it in the object first and then if it does not find it, it does lookups to the containing scopes until reaching the global one.

#### The problem
Although with allows a nice syntax to access/modify properties of an object, it can lead to undesired outcomes and errors. <br>
Consider the following example:

```js
function boo () {

  var person = {
    age: 22,
  }

  var name;

  with(person){

    name = "seif";
    job = "JavaScript Developer";
  }

  console.log(person.name);
  console.log(person.job);
  console.log(name);

}

boo();

console.log(job);
```

**Guess what will be the output?** <br>
```
undefined
undefined
seif
JavaScript Developer
```
**But why?** <br>
This is due to the lookups that the engine does when assigning values to the variables name and job.
