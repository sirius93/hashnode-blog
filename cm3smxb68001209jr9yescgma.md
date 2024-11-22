---
title: "Yet another blog on Call, Apply & Bind..!!"
seoTitle: "Yet another blog on Call, Apply & Bind..!!"
seoDescription: "How to answer the question : Explain Call, Bind & Apply in Javascript."
datePublished: Fri Nov 22 2024 11:05:15 GMT+0000 (Coordinated Universal Time)
cuid: cm3smxb68001209jr9yescgma
slug: yet-another-blog-on-call-apply-bind
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1732273207021/92fa831e-80f5-415e-b1ab-9e46cb5b6998.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1732273495482/3a810f53-ccfc-4da3-96b0-ce4f3221d51f.png
tags: javascript, learning, objects, this-keyword

---

## Bla Bla Bla..

Okay, Hear me out..!!

Hundreds of blogs and tutorials explain call, bind, and apply. Heck, even ChatGPT and Copilot can simplify them for you!

So why another post? Well, this one’s not for *you*—it’s my self-note as I revisit JavaScript fundamentals.

Even after 8 years in front-end development, I sometimes mix up these methods. Turns out, the confusion often stems from how they’re grouped in interview questions. Let me break it down for you—this time, in a way that sticks.

## Can we skip to the good part.

Why is it always call, bind, and apply in interviews? Functionally, call and apply are closer—they invoke the function immediately—while bind returns a new function. That’s why I’ve grouped them this way in the title.

Let's look at their usage to understand it better.

### What is common among Call, Bind & Apply?

**call**, **bind**, and **apply** are methods available on functions that allow you to explicitly set the value of **this** and pass arguments to the function.

### What is the difference between Call, Bind & Apply?

While Call and Apply Immediately invoke the function, the Bind method does not immediately invoke the function. instead, it returns a new function with **this** set to a specified value, and this returned function can be invoked/executed later.

### What is the difference between Call and Apply then?

While both Call and Apply immediately invoke the function with the custom this, it’s how they take the additional argument that differentiates them.

While Call takes the individual arguments, Apply takes an array of arguments.

### Examples

Let’s look at the below argument to understand the use of call, apply and bind.

```javascript
function Greetings(greeting,punctuation){
    return `${greeting} ${this.name} ${punctuation}`
}

var person = {
    name : "Nandan"
}

// Call: Immediately invokes the function with individual arguments
console.log(Greetings.call(person,"Hello","!")); // Output : Hello Nandan !

// Apply: Immediately invokes the function, but takes arguments as an array
console.log(Greetings.apply(person,["Hello","!"])); // Output : Hello Nandan !

// Bind: Returns a new function with `this` bound to the specified value
let greet = Greetings.bind(person,"Hello","!");
console.log(greet()); // Output : Hello Nandan !

//Note:
console.log(Greetings.bind(person,"Hello","!")); // Output : It will return a function
```

### Some Additional Examples

• **Using** call**:** Borrowing methods from another object:

```javascript
let person1 = { name: "Nandan" };
let person2 = { name: "Kumar" };

function introduce() {
    console.log(`Hi, my name is ${this.name}`);
}

introduce.call(person1); // Hi, my name is Nandan
introduce.call(person2); // Hi, my name is Kumar
```

• **Using** apply**:** Finding the max value in an array:

```javascript
let numbers = [1, 2, 3, 4, 5];
console.log(Math.max.apply(null, numbers)); // 5
```

• **Using** bind**:** Event handling with custom this:

```javascript
let button = document.getElementById("myButton");
let user = {
    name: "Nandan",
    greet() {
        console.log(`Hello, ${this.name}`);
    }
};

button.addEventListener("click", user.greet.bind(user));
```

Additionally, I hope this table will help you understand it better.

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Feature</strong></p></td><td colspan="1" rowspan="1"><p><strong>Execution</strong></p></td><td colspan="1" rowspan="1"><p><strong>Arguments</strong></p></td><td colspan="1" rowspan="1"><p><strong>Use Case</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>call</strong></p></td><td colspan="1" rowspan="1"><p>Executes the function immediately</p></td><td colspan="1" rowspan="1"><p>Passed individually</p></td><td colspan="1" rowspan="1"><p>When you know arguments at call time</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>apply</strong></p></td><td colspan="1" rowspan="1"><p>Executes the function immediately</p></td><td colspan="1" rowspan="1"><p>Passed as an array</p></td><td colspan="1" rowspan="1"><p>When arguments are in an array</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>bind</strong></p></td><td colspan="1" rowspan="1"><p>Returns a new function (does not execute)</p></td><td colspan="1" rowspan="1"><p>Optionally pre-filled for the new function</p></td><td colspan="1" rowspan="1"><p>When you need a reusable or pre-configured function</p></td></tr></tbody></table>

That’s all, folks! I hope you found this short note on Call, Apply & Bind helpful. If you enjoyed this, check out more articles on my website, [**https://nandan.dev/**](https://nandan.dev/)

Feel free to comment, email me at [**connect@nandan.dev**](http://mailto:connect@nandan.dev/), or connect with me on Twitter, Instagram, or GitHub. Don’t forget to subscribe to my newsletter for regular updates on JavaScript topics!

[**Twitter**](https://twitter.com/_sirius93_) | [**Instagram**](https://www.instagram.com/nandandotdev) | [**Github**](https://github.com/sirius93) | [**Website**](https://nandan.dev/)