# Part 01 — Callbacks

## What is a Callback?

A function passed into another function as an argument.

```js
function greet(name) {
  console.log("Hello " + name)
}

function processUser(name, callback) {
  console.log("Processing...")
  callback(name)
}

processUser("Ali", greet)
// Processing...
// Hello Ali ✅
```

---

## Callbacks are everywhere

```js
setTimeout(function() {
  console.log("done")
}, 2000)

btn.addEventListener("click", function() {
  console.log("clicked")
})

arr.forEach(function(value) {
  console.log(value)
})
```

---

## The Problem — Callback Hell

```js
setTimeout(function() {
  console.log("step 1")
  setTimeout(function() {
    console.log("step 2")
    setTimeout(function() {
      console.log("step 3") // unreadable ❌
    }, 1000)
  }, 1000)
}, 1000)
```

Nested callbacks become impossible to read and maintain.

This is called Callback Hell — Promises solve this.

---

## Quick Reference

| | Callback |
|---|---|
| What it is | Function passed as argument |
| Problem | Callback Hell |
| Solution | Promises |

> JavaScript Async Series
