---
title: "What are Javascript Closures?"
seoTitle: "What are Javascript Closures?"
seoDescription: "What are Javascript Closures? Front End Series."
datePublished: Mon Nov 18 2024 17:04:39 GMT+0000 (Coordinated Universal Time)
cuid: cm3na036c000209l2e8nfhrmt
slug: what-are-javascript-closures
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1731949387166/3ba3dbdd-5437-4a59-92a0-633e5d59405d.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1731949409814/bf08b0d1-af38-4332-b2df-eb610a160372.png
tags: javascript, interview-questions, lexical-scope, closures-in-javascript

---

Closures are a fundamental concept in JavaScript that enables powerful features like data privacy, state persistence, and functional programming. This blog will demystify closures with examples and practical use cases.

## When are closures created?

Closures are created when a function **(inner function)** is defined inside another function **(outer function).** The inner function has access to the outer function's lexical scope **(variables)** even after the outer function is executed.

### Lexical Scope in Javascript

Lexical scope means a function’s scope is determined by where it is written in the code, not where it is executed. This allows inner functions to access variables from their outer functions even if the outer function has already finished executing.

### Usage

Closures are used for creating Private variables and persistent States (Cache, Memoisation etc.).

### Closures with Examples

**A Simple counter**

```javascript
function Outer() {
    let count = 0; // count is a private variable
    return function inner() {
        count++; // count is updated every time inner is called
        return count; // the updated value of count is returned
    };
}

let Counter = Outer(); 
Counter(); // 1 (count starts at 0, incremented to 1)
Counter(); // 2 (incremented again)
Counter(); // 3
```

**Building a cache leveraging closure**

```javascript
function ObjectCache() {
    let Obj = {}; // Obj acts as a private cache
    return function ObjectUpdate(key, value) {
        if (!Obj[key]) {
            Obj[key] = value; // Add key-value to cache if not already present
            return Obj; // Return updated cache
        } else {
            return new Error("Duplicate Key"); // Prevent overwriting
        }
    };
}

let cache = ObjectCache();
cache("a", "b"); // {a: 'b'}
cache("a", "c"); // Error: Duplicate Key
cache("alpha", "romeo"); // {a: 'b', alpha: 'romeo'}
```

### Real World Examples

**Event Listeners - Click Counter**

```javascript
function attachListener(element) {
    let count = 0;
    element.addEventListener('click', () => {
        count++;
        console.log(`Clicked ${count} times`);
    });
}
```

**A Better Counter**

```javascript
const CounterModule = (() => {
    let count = 0;
    return {
        increment: () => ++count,
        reset: () => (count = 0),
        decrement: () => --count
    };
})();

CounterModule.increment(); // 1
CounterModule.increment(); // 2
CounterModule.decrement(); // 1
CounterModule.reset(); // 0
```

That’s all, folks! I hope you found this short blog on closures helpful. If you enjoyed this, check out more articles on my website, [https://nandan.dev/](https://nandan.dev/)

Feel free to comment, email me at [connect@nandan.dev](http://mailto:connect@nandan.dev), or connect with me on Twitter, Instagram, or GitHub. Don’t forget to subscribe to my newsletter for regular updates on JavaScript topics!

[Twitter](https://twitter.com/_sirius93_) | [Instagram](https://www.instagram.com/nandandotdev) | [Github](https://github.com/sirius93) | [Website](https://nandan.dev)