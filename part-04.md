# Part 04 — Fetch API

## What is Fetch API?

fetch() makes HTTP requests to a server and returns a Promise.

---

## Basic GET request

```js
async function getData() {
  try {
    let response = await fetch("https://jsonplaceholder.typicode.com/posts/1")
    let data = await response.json()
    console.log(data) ✅
  } catch(error) {
    console.log(error) ❌
  }
}

getData()
```

---

## Step by step

```js
// step 1 — make request
let response = await fetch("https://jsonplaceholder.typicode.com/posts/1")

// step 2 — check status
console.log(response.status) // 200 = success ✅

// step 3 — convert to JS object
let data = await response.json()

// step 4 — use the data
console.log(data.title)
```

---

## POST request — send data

```js
async function postData() {
  try {
    let response = await fetch("https://jsonplaceholder.typicode.com/posts", {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({
        title: "New Post",
        body: "This is the content"
      })
    })
    let data = await response.json()
    console.log(data) ✅
  } catch(error) {
    console.log(error) ❌
  }
}
```

---

## Quick Reference

| | Meaning |
|---|---|
| fetch(url) | Make a GET request |
| response.json() | Convert to JS object |
| response.status | HTTP status code |
| method: "POST" | Send data to server |
| body | Data to send |

>JavaScript Async Series
