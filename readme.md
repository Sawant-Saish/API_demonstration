# API Explanation for Beginners

---

## What is an API?

### Simple Definition

An **API (Application Programming Interface)** is a **bridge that allows two different software systems to communicate with each other**.

Your application does not directly access another application's database. Instead, it sends a request to an **API**, which then returns the required information.

---

## Real Life Analogy

Think of a **restaurant**:

1. You (user) choose food.
2. The **waiter (API)** takes your order.
3. The kitchen prepares the food.
4. The waiter brings the food back.

| Component | Real World        | Software            |
| --------- | ----------------- | ------------------- |
| Customer  | User              | Frontend App        |
| Waiter    | API               | Communication Layer |
| Kitchen   | Server / Database | Data Provider       |

---

## The API acts as the waiter between the client and the server

The API receives the request from the client, communicates with the server or database, and returns the response.

---

## Why APIs Are Important

APIs allow developers to:

- Get **weather data**
- Show **Google Maps**
- Process **online payments**
- Fetch **movie information**

Without APIs, applications would not be able to easily communicate with other systems.

---

# Example (Weather App)

```javascript
fetch("https://api.openweathermap.org/data");
```

### What happens here?

1. Your app sends a request to the **Weather API**
2. The API finds the requested data
3. The API sends the weather information back

So the **API acts like a data provider**.

---

# API Request Flow

```
Your Website
     ↓
fetch() sends request
     ↓
API Server
     ↓
Server sends data back
```

---

# Understanding `.then()`

### What `.then()` means

`.then()` runs **after the API response is received**.

```
Send API request
      ↓
Wait for response
      ↓
.then() executes
```

---

# What is `response`?

The API sends back a **response object**.

Example:

```javascript
Response {
  status: 200,
  headers: ...
  body: JSON data
}
```

But the data is still in **JSON format**, which JavaScript cannot directly use.

So we convert it using:

```javascript
response.json();
```

This converts the response **into a usable JavaScript object**.

---

# Getting the Actual Data

```javascript
.then(data => {
```

Now the JSON has been converted to **JavaScript data**.

Example data returned from the API:

```javascript
[
  { id: 1, name: "Leanne Graham", email: "leanne@gmail.com" },
  { id: 2, name: "Ervin Howell", email: "ervin@gmail.com" },
];
```

So now:

```
data = array of users
```

---

# Complete Flow

```
User clicks button
        ↓
fetch() sends API request
        ↓
Server sends response
        ↓
.then() converts response to JSON
        ↓
.then(data) gets user data
        ↓
Loop through users
        ↓
Display users on webpage
        ↓
.catch() handles errors
```

---

## Status Codes

A status code is a number returned by the server that tells us whether the API request succeeded or failed.

- 100–199 → Informational
- 200–299 → Success
- 300–399 → Redirection
- 400–499 → Client Errors
- 500–599 → Server Errors

--
