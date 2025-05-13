---
title: "Polyfills of JS Array Methods - Flat, Map, Filter & Reduce (Because Why Not?)"
seoTitle: "Polyfills for JS Array Methods: Enhance with Ease"
seoDescription: "Learn to build polyfills for JavaScript array methods flat, map, filter, and reduce, enhancing your skills and interview confidence"
datePublished: Tue May 13 2025 14:03:11 GMT+0000 (Coordinated Universal Time)
cuid: cmaml0no6000109ice2yt2s08
slug: polyfills-of-js-array-methods-flat-map-filter-and-reduce-because-why-not
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1747144915746/c275448b-a46c-4dad-8d0f-7d63dd154f7e.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1747144959434/72179926-54bc-403c-8123-169de4c59676.png
tags: javascript, array-methods, polyfills

---

Alright, confession time, I’ve been writing JavaScript for a while now, but there’s something oddly satisfying about going back to the basics. You know, like trying to bake your bread from scratch even though you live next to a bakery. That’s exactly what this post is about: baking our versions of some classic array methods.

Want to understand what polyfills are? [I have covered them in my blog Polyfills for Call, Apply & Bind.](https://blog.nandan.dev/polyfills-for-call-apply-and-bind-lets-build-them-from-scratch)

Why? Because it's fun. Because it's educational. And because the next time someone throws a technical interview curveball at you, like "Can you write your own `reduce`" and you’ll casually say, "Sure, do you want it with comments or without?"

Today, we’re building polyfills for:

* `flat()`
    
* `map()`
    
* `filter()`
    
* `reduce()`
    

Let’s roll.

## `flat()` — A Pancake Stack for Arrays

```javascript
if(!Array.prototype.myFlat){
    Array.prototype.myFlat = function(depth){
        if(depth < 0) return this;
        
        const flatten = function(arr, depth){
            return arr.reduce((acc,ele)=>{
                if(Array.isArray(ele) && depth > 0){
                    acc = acc.concat(flatten(ele,depth -1));
                }else{
                    acc.push(ele);
                }
                return acc;
            },[])
        }
        
        return flatten(this,depth);
    }
}

const nestedArray = [1, [2, [3, [4, 5]]], 6];

console.log(nestedArray.myFlat()); // Default depth = 1 => [1, 2, [3, [4, 5]], 6]
console.log(nestedArray.myFlat(2)); // Depth = 2 => [1, 2, 3, [4, 5], 6]
console.log(nestedArray.myFlat(3)); // Depth = 3 => [1, 2, 3, 4, 5, 6]
console.log(nestedArray.myFlat(0)); // Depth = 0 => [1, [2, [3, [4, 5]]], 6]
```

Just a basic flattening function. Will it replace your backend job? No. But will it make you feel cool? Absolutely.

## `map()` — Because Sometimes Arrays Need a Makeover

```javascript
if(!Array.prototype.myMap){
    Array.prototype.myMap = function(fn, thisArg){
       if(this == null)  { return new Error("Not an array")};
       
       if(typeof(fn) != 'function') {return new Error("Not an array")}
       
       let result = [];
       
       for(let i=0; i< this.length; i++){
           if(i in this){
               result.push(fn.call(thisArg,this[i], i, this));
           }
       }
       return result;
    }
}

a = [1,2,3,4,5].myMap(function (mem) {
    return mem*mem;
})

console.log(a); // [ 1, 4, 9, 16, 25 ]
```

Simple and clean. No magical spells involved.

## `filter()` — Only the Worthy Shall Pass

```javascript
if(!Array.prototype.myFilter){
    Array.prototype.myFilter = function(fn, thisArg){
       if(this == null)  { return new Error("Not an array")};
       
       if(typeof(fn) != 'function') {return new Error("Not an array")}
       
       let result = [];
       
       for(let i=0; i< this.length; i++){
           if(i in this && fn.call(thisArg,this[i], i, this)){
               result.push(this[i]);
           }
       }
       return result;
    }
}

b = [1,2,3,4,5].myFilter(function (mem) {
    return mem > 1;
})

console.log(b) //[ 2, 3, 4, 5 ]
```

Give it a test run with your own weird conditions. Even filter out people who don't like coffee; your call.

## `reduce()` — The Boss Level

```javascript
if(!Array.prototype.myReduce){
    Array.prototype.myReduce = function(callback,initialValue){
        if(this == null) {return new Error("Not an Array");}
        
        if(typeof(callback) != 'function') {
            return new Error("Not a function");
        }
        
        let arr = this;
        let len = arr.length;
        
        let hasInitial = arguments.length > 1;
        let accumulator = hasInitial ? initialValue : arr[0];
        let startIndex = hasInitial ? 0 : 1;
    
        if (len === 0 && !hasInitial) {
          throw new Error("Reduce of empty array with no initial value");
        }
        
        
        for (let i = startIndex; i < len; i++) {
          if (i in arr) {
            accumulator = callback(accumulator, arr[i], i, arr);
          }
        }
    
        return accumulator;
    }
}

let a = [1, 2, 3].myReduce((acc, val) => acc + val, 0);
console.log(a);
```

Reduce is like that friend who seems intimidating at first, but once you get to know them, they carry the whole squad.

### Why Do This?

You may never need to use these in a production app. But knowing how they work helps you:

* Understand JavaScript fundamentals better.
    
* Appreciate the built-in methods more.
    
* Have something cool to say in interviews or while pretending to debug in coffee shops.
    

So go ahead, mess around with these, add your own flavour, and maybe even extend a couple more methods just for fun.

That’s all, folks! I hope you found this helpful. If you enjoyed this, check out more articles on my Blog, [https://blog.nandan.dev/](https://blog.nandan.dev/)

Feel free to comment, email me at [**connect@nandan.dev**](http://mailto:connect@nandan.dev/), or connect with me on Twitter, Instagram, or GitHub. Don’t forget to subscribe to my newsletter for regular updates on JavaScript topics!

[**Twitter**](https://twitter.com/_sirius93_) | [**Instagram**](https://www.instagram.com/nandandotdev) | [**Github**](https://github.com/sirius93) | [**Website**](https://nandan.dev/)