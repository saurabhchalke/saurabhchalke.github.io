---
title: Venturing into the World of FizzBuzz with JavaScript
published: true
---

In the vast expanse of programming, there lies a riddle—a riddle so simple yet profound, often whispered in hushed tones among the coding community. Its name? *FizzBuzz*. Some say it's a test of basic logic, while others see it as a playful way to hone one's coding skills.

Today, we're not just discussing the enigma of FizzBuzz, but we'll also be exploring its various manifestations in the wonderful world of JavaScript.

## The Riddle of FizzBuzz

For the uninitiated, here's the FizzBuzz challenge: Write a program that prints numbers from 1 to 100. But there's a twist!

- If a number is divisible by 3, print "Fizz".
- If it's divisible by 5, print "Buzz".
- If it's divisible by both 3 and 5, you got it, print "FizzBuzz".
- Otherwise, simply print the number.

Sounds fun? Let’s jump into the code!

### The Classic Approach

```js
const fizzbuzz = (n) => {
    for (let i = 1; i <= n; i++) {
        if (i % 15 == 0) console.log('FizzBuzz');
        else if (i % 3 == 0) console.log('Fizz');
        else if (i % 5 == 0) console.log('Buzz');
        else console.log(i);
    }
}
```

For those reminiscing Python, yes, I did skip the curly brackets for brevity. But for the purists among you:
  
```js
const fizzbuzz = (n) => {
    for (let i = 1; i <= n; i++) {
        if (i % 15 == 0) {
            console.log('FizzBuzz');
        } else if (i % 3 == 0) {
            console.log('Fizz');
        } else if (i % 5 == 0) {
            console.log('Buzz');
        } else {
            console.log(i);
        }
    }
}
```

Let's see what happens if we call this function with the number 30 (well yea, it's 1 to 30).

```bash
$ node fizz-buzz.js
1
2
Fizz
4
Buzz
Fizz
7
8
Fizz
Buzz
11
Fizz
13
14
FizzBuzz
16
17
Fizz
19
Buzz
Fizz
22
23
Fizz
Buzz
26
Fizz
28
29
FizzBuzz
```

## A More Elegant Touch

But what if we don't want to flood our console? Let's neatly package our output into an array.

```js
const fizzbuzz = (n) => {
    let array = [];
    for (let i = 1; i <= n; i++) {
        if (i % 15 == 0) array.push('FizzBuzz');
        else if (i % 3 == 0) array.push('Fizz');
        else if (i % 5 == 0) array.push('Buzz');
        else array.push(i);
    }
    return array;
}

console.log(fizzbuzz(100));
```

For those who enjoy a switch in their step, here's an alternative solution:

```js
const fizzbuzz = (n) => {
    let array = [];
    for (let i = 1; i <= n; i++) {
        switch (true) { 
            case i % 15 === 0: array.push('FizzBuzz'); break;
            case i % 3 === 0: array.push('Fizz'); break;
            case i % 5 === 0: array.push('Buzz'); break;
            default: array.push(i);
        }
    }
    return array;
}
```

## A Brief Dive into JS Syntax

Before we conclude, let's shed some light on JavaScript functions.

Traditional function declaration:

```js
function some_function() {
    // Code here
}
```

But JS, being the hipster language that it is, also offers arrow functions:

```js
const some_function = () => {
    // Code here
}
```

Remember, const declares a read-only reference. So, it's perfect for our function, ensuring it remains unaltered. For variables that change, like our array, the let keyword comes to the rescue.

Hungry for more JS knowledge? Dive deep into the [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript) or the official JavaScript [documentation](https://devdocs.io/javascript/).

Thank you, dear reader, for embarking on this journey with me. May your code always run error-free!
