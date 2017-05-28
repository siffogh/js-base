# Hoisting

## Undefined & ReferenceError

There are two cases to be aware of when accessing RHS:

- Accessing a declared non-initialized variable:

```js
var x;
console.log(x);
```
The output will be **undefined**

- Accessing a non-declared variable:

```js
console.log(x);
```

This will result in a **ReferenceError**.

## The Truth about order of execution

<img src="https://github.com/siffogh/seif-gifs/raw/master/lie.png" style="max-height:200px"/>


Let's take an example:

```js
console.log(a);
var a;
```

Let's assume the engine goes through code line by line. When the engine executes the 1st line, the expected output is "Uncaught ReferenceError" since a was not defined yet.

But hey guess what ??

<img src="https://github.com/siffogh/seif-gifs/raw/master/wrong.jpg" style="max-height:200px"/>


## Hoisting

In fact, before executing anything the engine goes through the process of [compilation](scope_explained.md). It looks first for all types declarations (variable or function) and shifts them to the top of its memory before executing the code. This is what we call **Hoisting**.

Therefore, the previous code is executed as if it was written in this way:
```js
var a;
console.log(a);
```

### Another Example

```js
foo();

function foo() {
  console.log('hello!');
}

```

Due to hoisting, the engine executes this code in this way:

```js
function foo() {
  console.log('hello!');
}

foo();

```