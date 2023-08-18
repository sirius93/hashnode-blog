---
title: "Design Patterns: Module Design Pattern in JavaScript"
seoTitle: "Design Patterns: Module Design Pattern in JavaScript"
seoDescription: "Design Patterns: Module Design Pattern in JavaScript - By -Nandan Kumar"
datePublished: Fri Aug 18 2023 16:41:07 GMT+0000 (Coordinated Universal Time)
cuid: cllgthof3000909i8dw1fhxe0
slug: design-patterns-module-design-pattern-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692376676555/d6d19109-6e9f-4605-864b-83682ab0f4b7.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1692376842749/f2d6456c-2afb-4239-b903-f155d982d2b9.png
tags: design-patterns, javascript, web-development, learn-coding, module-pattern

---

Module Design Pattern is a way to encapsulate and organize code in a self-containing module that can expose certain functionalities while keeping the rest of the code private.

This helps prevent variable and function name clashes, improves code maintainability, and promotes the concept of separation of concerns.

Here's an example of how you can implement the Module Design Pattern in JavaScript:

```javascript
// Module using the Module Design Pattern
var Module = (function() {
  // Private variable
  var privateVariable = "I am a private variable";

  // Private function
  var privateFunction = function privateFunction() {
    console.log("This is a private function");
  }

  // Public function
  var publicFunction = function() {
      console.log("This is a public function");
  }
  // Public interface
  return {
    publicFunction:publicFunction,
    // Public variable accessing private variable
    publicVariable: privateVariable
  };
})();

// Usage of the module
console.log(Module.publicVariable); // Output: "I am a private variable"
Module.publicFunction(); // Output: "This is a public function"

// Trying to access private members directly (will result in an error)
console.log(Module.privateVariable); // Output: undefined
Module.privateFunction(); // Output: Uncaught TypeError: MyModule.privateFunction is not a function
```

In the above example, we've created a module called `Module` using an **Immediately Invoked Function Expression (IIFE)**. Inside the IIFE, we define private variables and functions that are not accessible from outside the module. We then return an object containing the public members (functions and variables) that we want to expose.

Benefits of the Module Design Pattern:

1. **Encapsulation:** Private members are not accessible from outside the module, which helps prevent unintended modifications or conflicts with other parts of the codebase.
    
2. **Organization:** Code is organized into logical modules, making it easier to manage and understand.
    
3. **Namespacing:** The module acts as a namespace, reducing the chances of naming collisions in a global scope.
    
4. **Reusability:** Modules can be easily reused in different parts of your application or different projects.
    
5. **Maintenance:** Separation of concerns and encapsulation make it easier to maintain and refactor code.
    

That's a concise explanation of the module design pattern in Javascript.

Feel free to comment on how you like my blog or shoot me a mail at [**connect@nandan.dev**](mailto:connect@nandan.dev) If you have any queries and I will try to answer.

You can also visit my website to read some of the articles at [**nandan.dev**](http://nandan.dev)

Stay tuned & connect with me on my social media channels. Make sure to subscribe to my newsletter to get regular updates on my upcoming posts.

[**Twitter**](https://twitter.com/_sirius93_) | [**Instagram**](https://www.instagram.com/_sirius93_) | [**Github**](https://github.com/sirius93) | [**Website**](https://nandan.dev/)