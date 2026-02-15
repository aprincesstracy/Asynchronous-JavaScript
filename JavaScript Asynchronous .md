Asynchronous JavaScript (Concise Guide)

Asynchronous JavaScript allows tasks like API calls, timers, and file operations to run without blocking the main thread, keeping applications responsive.

I Learned;
🔹 1. Synchronous vs Asynchronous

Synchronous → The code runs line by line.

Asynchronous →The some tasks run in the background.

console.log("Start");

setTimeout(() => {
  console.log("Delayed");
}, 1000);

console.log("End");


Output:

Start
End
Delayed

🔹 2.I learned about Callbacks

A callback is a function passed into another function to execute later.

function fetchData(callback) {
  setTimeout(() => {
    callback("Data received");
  }, 1000);
}

fetchData(data => console.log(data));


⚠️ Deep nesting of callbacks can lead to callback hell.

🔹 3.I learned about Promises

A Promise represents a value that will be resolved or rejected in the future.

let promise = new Promise((resolve, reject) => {
  resolve("Success!");
});

promise
  .then(result => console.log(result))
  .catch(error => console.log(error));


States:

pending

fulfilled

rejected

I learned;
🔹 4. Async / Await

It is a cleaner syntax built on Promises.

function delay() {
  return new Promise(resolve =>
    setTimeout(() => resolve("Done!"), 1000)
  );
}

async function run() {
  let result = await delay();
  console.log(result);
}

run();


Use try...catch for error handling.

🔹 5.I learned Fetch Example
async function getData() {
  try {
    let response = await fetch("https://api.example.com");
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.log("Error:", error);
  }
}
