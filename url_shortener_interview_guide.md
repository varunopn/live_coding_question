# URL Shortener - 30 Minute Interview Problem

## Problem Statement
Build a simple URL shortening service with REST API endpoints. The service should allow users to create shortened URLs and retrieve original URLs.

---

## Required Endpoints

### 1. POST `/shorten`
Create a shortened URL from a long URL.

**Request Body:**
```json
{
  "url": "https://www.example.com/very/long/path?query=params",
  "customAlias": "optional-custom-code"  // Optional
}
```

**Success Response (201 Created):**
```json
{
  "shortUrl": "http://short.ly/abc123",
  "shortCode": "abc123",
  "originalUrl": "https://www.example.com/very/long/path?query=params"
}
```

**Error Responses:**
- 400 Bad Request - Invalid URL format
- 409 Conflict - Custom alias already exists

---

### 2. GET `/{shortCode}`
Redirect to the original URL.

**Success Response (302 Found):**
- Redirect to original URL via `Location` header

**Error Response:**
- 404 Not Found - Short code doesn't exist

---

## Requirements

### Must Have:
- Valid URL validation (check format, protocol)
- Generate random short codes (6-8 characters)
- Store mappings (in-memory Map/Dictionary is fine)
- Proper HTTP status codes
- Basic error handling
