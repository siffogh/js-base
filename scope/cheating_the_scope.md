### Cheating the Scope
> **Notice:** <br>
The 2 techniques we are going to see are deprecated.

#### with keyword
The _with_ keyword allows to access/modify the values of an object with a simpler syntax. <br>

##### eg:-

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

##### What just happened ?

<img src="https://github.com/siffogh/seif-gifs/raw/master/wow-gif.gif" style="max-height:200px"/>

When executing the body of _with_, the engine does the following:
- creates a specific scope attached to the body of person.
- when assigning/accessing any property, it looks for it in the object first and then if it does not find it, it does lookups to the containing scopes until reaching the global one.

##### The problem
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

#### eval function

##### eg:-

```js
function foo () {
  eval('var x = 10;')
  console.log(x);
}
foo();
```

##### What just happened ?

<img src="https://github.com/siffogh/seif-gifs/raw/master/wow-gif.gif" style="max-height:200px"/>

_eval_ allows to evaluate a string as javascript code as if it was inserted there as normal code.

The previous code will have the same result as:

```js
function foo () {
  var x = 10;
  console.log(x);
}
foo();
```

##### The problem
- slower execution because the code is inserted at runtime.
- might be dangerous if used to evaluate a malicious piece of code.
