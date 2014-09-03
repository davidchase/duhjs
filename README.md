Duh.js
=====

Straightforward Style Guide for Javascript.

After reading this all that should come to your mind is `duh!`.

Why?
---
Yes everyone and their neighbor has one, so why not another one.

Preface
-------
These are my ideas that I use to code with `if you don't like it don't use it.`

Simple as that.

'use strict';
-------------
```js
// top of the module
'use strict';
```
I write modules aka [commonjs](http://wiki.commonjs.org/wiki/Modules/1.0) maybe later a little `es6`
so I begin each file with one of these guys `'use strict'`.

If you are into closures to avoid global messiness then do
```js
(function(){
  'use strict';  

})();
```

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

It easy to read and understand, and keeps the constructor capitalize 
first letter true to form. 

EventEmitter is prettier than Eventemitter... but thats just me

Variables
---------
```js
// one var per line
var foo;
var bar = 0;
var fooBar = 'some string';

// I also declare variables on top of my functional scope.
var myMethod = function() {
    // variables scoped to method
    var someVar;
}

```

Easy to read, don't care about saving a few keys.


Functions
---------
```js
// I prefer function expressions
// delcare functions before using them.

// first create
var foo = function(){};
var baz = function(){};

// then use :)
foo();
baz();
```
It makes sense to first create something or require something before using it.

Since the functions are on top of the scope in this case the file, hoisting isn't an issue.


Requires
--------
```js
// Requires on top just like functions
// commonjs FTW
var http = require('http');
var cluster = require('cluster');
var someFunction = require('./lib/someFunction');

http.createServer(requestListener);

```
When writing [node](http://nodejs.org/) or [browserify](http://browserify.org/) based code requiring libraries or classes 
works in the same pattern. 

Require core or external libraries first followed by local to the project.

Switches
--------
Don't like them, don't use em!
```js
// I group items in a dictionary list or object literal instead
var actions = {
    'action': function(){},
    'anotherAction': function(){},
    'tertiaryAction': function(){}
}

// use it
if (typeof actions[action] === 'function') {
    actions[action].call(null);
}
```

Patterns
--------
Use them and use them right!

Patterns are great for avoiding spaghetti code you **don't** need a framework for [that](http://www.faqs.org/docs/artu/ch01s06.html).

If you don't know what `this` is referencing at all times [then you don't know javascript](http://goo.gl/BAEclg)

```js
// Constructor pattern
var Robot = function(name, age){
    this.name = name;
    this.age = age;
}

Robot.prototype.getAge = function(){
    return this.age;
}

Robot.prototype.beepBoop = function(){
    return 'beep beep boop';  
};

// export that goodness
module.exports = Robot;

// If you want you can do
// this organize the prototypes in a literal
// but don't forget to set the constructor otherwise it will point to native `Object`

Robot.prototype = {
    constructor: Robot,
    getAge = function(){
        return this.age;
    },
    beepBoop = function(){
        return 'beep beep boop';  
    }
}

```
