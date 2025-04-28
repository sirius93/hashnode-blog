---
title: "Polyfills for Call, Apply, and Bind — Let’s Build Them From Scratch"
seoTitle: "Creating Polyfills for Call, Apply, Bind"
seoDescription: "Learn to create polyfills for call, apply, and bind in JavaScript, demystifying these essential function manipulation methods"
datePublished: Mon Apr 28 2025 16:51:28 GMT+0000 (Coordinated Universal Time)
cuid: cma1bfahn000h09l8eouf4tur
slug: polyfills-for-call-apply-and-bind-lets-build-them-from-scratch
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1745858731907/fc43c7fc-0191-42ff-bdd1-19518625c8b7.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1745859064653/781c17cf-fc00-4866-a29b-2a9cd993bbf2.png
tags: javascript, interview-questions, polyfills, call-apply-and-bind-methods

---

%[https://store.nandan.dev/l/javascript-interview-prep-handbook] 

Okay, so if you have ever deep-dived into JavaScript interviews or just casually scrolled through dev Twitter (yes, that’s a thing), you would have stumbled upon someone throwing around the words **polyfill** like they were born building web browsers.

And if you’re like me, you probably nodded along, opened a tab to Google it later, and… procrastinated.

![](https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExd2NhODEycGhiZjJmZGsweG4xaHc5ODAzbnB0eGk4dWZjM241Yjd4YSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/3o6gbenQcUjEGTaNfW/giphy.gif align="center")

But no worries. You’re here now, and we are going to figure this out *together.*

## **First things first — What the heck is a polyfill?**

A **polyfill** is just a piece of code (usually JavaScript) that **adds functionality to older browsers** that do not natively support a certain feature.

Think of it like you bringing a power bank to an event where there are no charging points. Your phone is old? No problem. You got the backup.

## **Now… Why Call, Apply, and Bind?**

Because they’re like the Avengers of function manipulation in JavaScript.

And also because they confuse almost everyone at first.

* `call` lets you call a function with a given this value and arguments.
    
* `apply` is like `call`, but arguments are passed as an array.
    
* `bind` doesn’t immediately invoke the function. It *returns a new function* with a given this.
    

[Here is a detailed write-up on call, apply & bind](https://blog.nandan.dev/yet-another-blog-on-call-apply-bind).

Simple enough, right? Now let’s make our versions

## **Polyfill for call**

Here’s how we can build a **polyfill for call**:

```javascript
Function.prototype.myCall = function(context,...args){ 
    context = context || globalThis;
    let Symbolfn = Symbol("fn"); // Unique key
    context[Symbolfn] = this; // Assign 'this' function to the context
    let result = context[Symbolfn](...args); // Call the function
    delete context[Symbolfn];  // Clean up
    return result;
}

// Usage
function sayHello(greeting) {
  console.log(`${greeting}, ${this.name}`);
}

const user = { name: "Nandan" };
sayHello.myCall(user, "Hello");
```

Cool, right? Not rocket science.

## **Polyfill for apply**

Now, let’s tweak it a bit for **apply**:

```javascript
Function.prototype.myApply = function(context,args){
    context = context || globalThis;
    let Symbolfn = Symbol("fn");
    context[Symbolfn] = this;
    let result = args ? context[Symbolfn](...args) : context[Symbolfn]();
    delete context[Symbolfn];
    return result;
}

// Usage
sayHello.myApply(user, ["Hi"]);
```

## **Polyfill for bind**

Now comes the big boss **bind**.

```javascript
Function.prototype.myBind = function(context,...initialArgs){
    let fn = this;
    return function(...functArgs){
        return fn.apply(context, [...initialArgs,...functArgs])
    }
}

// Usage
const boundSayHello = sayHello.myBind(user, "Hey");
boundSayHello(); // Outputs: Hey, Nandan
```

* bind doesn’t call the function right away.
    
* It returns a *new function* that you can call later.
    
* We merge the arguments provided at bind-time and call-time.
    

## **That’s it — You just built call, apply, and bind polyfills!**

Honestly, when I first read about polyfills, I thought it was some deep internal browser magic. Turns out, it’s just about creatively manipulating JavaScript’s behavior.

If you take one thing from this post, let it be this:

> “The cowards never started and the weak died along the way. That leaves us, ladies and gentlemen. Us.”

(Yeah, that’s a quote from *Shoe Dog*. Still fits perfectly here, doesn’t it?)

[Here’s one if you want to read a review of the book Shoe Dog, written by me.](https://kitaaben.com/p/just-do-it-the-real-story-behind-nike-s-rise)

That’s all, folks! I hope you found this short note on Polyfills of Call, Apply & Bind helpful. If you enjoyed this, check out more articles on my Blog, [https://blog.nandan.dev/](https://blog.nandan.dev/)

Feel free to comment, email me at [**connect@nandan.dev**](http://mailto:connect@nandan.dev/), or connect with me on Twitter, Instagram, or GitHub. Don’t forget to subscribe to my newsletter for regular updates on JavaScript topics!

[**Twitter**](https://twitter.com/_sirius93_) | [**Instagram**](https://www.instagram.com/nandandotdev) | [**Github**](https://github.com/sirius93) | [**Website**](https://nandan.dev/)