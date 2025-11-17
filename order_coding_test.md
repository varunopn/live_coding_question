# Node.js Live Coding Test – Orders API & Customer Summary

## Objective

Implement a small Node.js HTTP API that:

- Manages **orders** in memory (or use local database).
- Provides **CRUD endpoints** for order management.
- Provides an endpoint that **summarizes orders grouped by customer**.

You may use **Express** or Node.js built-in `http` module.

---

## Data Model

An **Order** consists of (or can come up by yourself):

```json
{
  "id": 1,
  "customerId": "A",
  "amount": 100
}
```

Data should be stored **in memory**, or local db/sql lite (up to your preference) for example:

```js
let orders = [];
```

---

## API Requirements

### 1. List Orders

**GET /orders**

- Returns all orders.
- Response status: `200 OK`

Example response:

```json
[
  { "id": 1, "customerId": "A", "amount": 100 },
  { "id": 2, "customerId": "B", "amount": 50 }
]
```

---

### 2. Get Single Order

**GET /orders/:id**

- Return order by `id`.
- If not found:
  - `404 Not Found`
  - JSON error message

---

### 3. Create Order

**POST /orders**

Request body example:

```json
{
  "customerId": "A",
  "amount": 100
}
```

Rules:

- `id` is generated on server.
- Validate:
  - `customerId` must be a non-empty string.
  - `amount` must be a positive number.

Response:

- `201 Created` + created order
- `400 Bad Request` on validation error

---

### 4. Update Order (Partial Update) [Optional can skip to save time]

**PATCH /orders/:id**

Example body:

```json
{
  "amount": 200
}
```

Rules:

- Only update provided fields.
- If order not found: `404 Not Found`
- On success: `200 OK` + updated order

---

### 5. Delete Order

**DELETE /orders/:id**

Rules:

- If not found: `404 Not Found`
- On success:
  - `204 No Content` (recommended), or
  - `200 OK` with confirmation message

---

## Customer Summary

### GET /summary/customers

This endpoint should:

- Group orders by `customerId`
- For each customer, calculate:
  - `totalAmount`
  - `orderCount`

Example:

Given:

```js
[
  { id: 1, customerId: "A", amount: 100 },
  { id: 2, customerId: "B", amount: 50 },
  { id: 3, customerId: "A", amount: 40 }
]
```

**Response:**

```json
{
  "A": { "totalAmount": 140, "orderCount": 2 },
  "B": { "totalAmount": 50, "orderCount": 1 }
}
```

If no orders exist → return `{}` (empty object).

---

## Technical Expectations

- Use Node.js (any recent LTS).
- JSON-only API.
- Use proper HTTP status codes.
- Handle common errors (invalid ID, invalid fields, missing order).

---


## Evaluation Criteria

- Understanding of Node.js/Express routing
- CRUD implementation quality
- Data transformation logic
- Error handling
- Clean code & readability

---

## Instructions

- Code may be in a single file or multiple files.
- Use any module system (CommonJS or ES modules).
- Explain your design decisions while coding.
