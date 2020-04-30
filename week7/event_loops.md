# What the hell is the event loop anyway?

The event loop exists within Javascript

&yet is who the presenter works for, they specialise in realtime stuff. He is a paid pro javascript developer.

So how does javascript work?

- V8
- Callbacks
- Single threaded

What does all this mean?

What is javascript?

- A single-threaded non-blocking asynchronous concurrent language

Huh?
What do you have?

- Has a call stack
- event loop
- Callback queue
- Other apis and stuff

What does V8 have?

- A call stack
- A heap 

## After 18 months of study

Javascript runtime in chrome is V8.

It has two components.

1. A heap - where memory allocation happens
2. A call stack - where stack frames are

If you clone the V8 codebase you will find there is no setTimeout, DOM, or XML HTTP request, they are not in there. They don't exist in V8.

setTimeout is one of the first things you use when you start learning about async and its not in the V8 source!

## Bigger picture

We have the V8 runtime, but also
- Web apis are extra things the browser provides - DOM, AJAX, setTimeout
- Event loop  
- Callback queue 

### The call stack

one thread == one call stack == one thing at a time

Javascript is single threaded, which means it has one call stack, which means it can only do one thing at a time. Thats what single threaded means, it can only do one thing at a time.

The call stack is a datastructure that records where in the program we are.

If we step into a function, we push something on the stack. If we return from a function we pop off the top of the stack.

Thats all the stack can do, push onto the top, pop off the top.

```javascript
function foo() {
  throw new Error('Oops!')
}
function bar() {
  foo()
}
function baz() {
  bar()
}
baz()
```
This run in the console shows
```
VM40:2 Uncaught Error: Oops!
    at foo (<anonymous>:2:9)
    at bar (<anonymous>:5:3)
    at baz (<anonymous>:8:3)
    at <anonymous>:10:1 ------> this is the main()
```
This error shows the stack trace!

We can also blow the stack.

```javascript
function foo() {
  return foo()
}
foo()
```
This returns the error
```
VM45:1 Uncaught RangeError: Maximum call stack size exceeded
    at foo (<anonymous>:1:13)
    at foo (<anonymous>:2:10)
    at foo (<anonymous>:2:10)
    at foo (<anonymous>:2:10)
    at foo (<anonymous>:2:10)
    at foo (<anonymous>:2:10)
    at foo (<anonymous>:2:10)
    at foo (<anonymous>:2:10)
    at foo (<anonymous>:2:10)
    at foo (<anonymous>:2:10)
```

This is recursively adding the same function lots of times to the call stack.

## Blocking

What happens when things are slow?

Blocking is code that is slow.

Things which are slow and are on that stack are blocking.

```javascript
var foo = $.getSync('//foo.com') ----> slow -> blocking

console.log(foo)
```

This is a problem when we are running code in the browser. The whole page freezes, the browser is blocked, it is stuck until the request is complete, then all hell breaks loose as it suddenly does all the things you've been clicking on while it seemed frozen.

This is not ideal for nice fluid UIs.

## Solutions?

 - Asynchronous callbacks.

```javascript
console.log('Hi');

setTimeout(function() {
  console.log('There');
}, 5000);

console.log('JSConfEU')
```

That queues the console.log for some time later.

### Async callbacks and the call stack

```javascript
console.log('hi') ---->goes on the stack
console.log('There'); ---> goes on and jumps off stack
console.log('JSConfEU') --> goes on the stack

console.log('There'); ---> after 5s jumps back on the stack
```

## Concurrency and the event loop

Javascript the run time can only do one thing at a time.
Yet we can do things concurrently, as the browser is more than just the runtime.

Thanks to the browsers web apis, it acts as if we had extra threads we can make calls to.

Those peices of the browser are aware this concurrency kicks in.

For node.js instead of web apis there are C++ APIs and the threading is being hidden from you by C++.

