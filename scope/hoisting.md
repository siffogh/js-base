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
