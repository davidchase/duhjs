Duh.js
=====

Straightforward Style Guide for Javascript.

Why?
---
Yes everyone and their neighbor has one, so why not another one.

Preface
-------
These are my ideas that I use to code with `if you don't like it don't use it.`

Simple as that.

Variables
---------
```js
// one var per line
var foo;
var bar = 0;
var fooBar = 'some string';
```

Easy to read, don't care about saving a few keys.

Naming
------
```js
// I like camelCase for functions and variables
// and PascalCase for longer constructors, etc

// function or variable
var fooBar;

// "long" constructor
var EventEmitter = function(){
    this.events;
}

// regular constructor
var Student = function(){
    this.name;
}

```

Functions
---------
```js
// I prefer function expressions
// delcare my functions before I use them.

// first create
var foo = function(){};
var baz = function(){};

// then use :)
foo();
baz();
```
It makes sense to first create something or require something before using it.


Requires
--------
```js
// Requires on top just like functions
// commonjs FTW
var http = require('http');
var cluster = require('cluster');
var someFunction = require('./lib/someFunction');

```