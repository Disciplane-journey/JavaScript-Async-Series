# Part 03 — Async/Await

## async keyword

Marks a function as asynchronous — it returns a Promise automatically.

```js
async function getData() {
  return "hello"
}

getData().then(result => console.log(result)) // "hello" ✅
```

---

## await keyword

Pauses the function until the Promise resolves.
Only works inside an async function.

```js
async function getData() {
  let response = await fetch("https://api.example.com/data")
  let data = await response.json()
  console.log(data) ✅
}
```

---

## Error handling with try/catch

```js
async function getData() {
  try {
    let response = await fetch("https://api.example.com/data")
    let data = await response.json()
    console.log(data) ✅
  } catch(error) {
    console.log(error) ❌
  }
}
```

---

## Promise vs Async/Await

```js
// Promise
fetch(url)
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.log(err))

// Async/Await — same result, cleaner
async function getData() {
  try {
    let res  = await fetch(url)
    let data = await res.json()
    console.log(data)
  } catch(err) {
    console.log(err)
  }
}
```

---

## Quick Reference

| | Meaning |
|---|---|
| async | Function returns a Promise |
| await | Wait for Promise to resolve |
| try | Code to run |
| catch | Handle errors |

> Part 03/04 — JavaScript Async Series
