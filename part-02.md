# Part 02 — Promises

## What is a Promise?

A value that is not available yet — but will be in the future.

3 states: Pending, Resolved, Rejected.

---

## Creating a Promise

```js
let promise = new Promise(function(resolve, reject) {
  let success = true

  if(success) {
    resolve("Data loaded") // ✅
  } else {
    reject("Something went wrong") // ❌
  }
})
```

---

## Using a Promise

```js
promise
  .then(function(result) {
    console.log(result) // runs on success ✅
  })
  .catch(function(error) {
    console.log(error) // runs on failure ❌
  })
  .finally(function() {
    console.log("always runs") // always ✅
  })
```

---

## Promise Chaining

```js
fetch("https://api.example.com/data")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.log(error))
```

No nesting. Clean and flat. ✅

---

## Quick Reference

| | Promise |
|---|---|
| Pending | Not done yet |
| Resolved | Success → .then() |
| Rejected | Failed → .catch() |
| Always | .finally() |

> Part 02/04 — JavaScript Async Series
