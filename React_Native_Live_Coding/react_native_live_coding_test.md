# React Native Live Coding Test

## Title: Login + Fetch Todo List App
**Difficulty:** Easy–Medium
**Estimated Time:** 30 minutes

---

## 🧪 Objective

Build a simple React Native app with:

1. A **Login screen** (basic validation only)
2. After login, fetch and display todos from an API

---

## 🧩 Requirements

### 1. Login Screen

Create a screen with:

- Email input
- Password input
- Login button

**Validation rules:**

- If email or password is empty → show error message:
  **“Please fill in all fields.”**
- If email does not contain "@" → show error message:
  **“Please enter a valid email.”**
- If inputs are valid → navigate to the **Todo List screen**
  (No real authentication needed)

---

### 2. Todo List Screen

After successful “login”, fetch todos from:

```
https://jsonplaceholder.typicode.com/todos
```

Your app must:

- Show a **loading indicator** while fetching
- Display **first 20 todos** in a list
- For each todo, display:
  - Title
  - Completion status (e.g., `✅` or `❌`)

(Optional)
If the API fails, show:

**“Failed to load todos.”**


---

## 📦 Expected Deliverable

A working React Native implementation with:

- Functional Login screen
- API fetch
- Todo list rendering

Allowed environments:

- Expo
- React Native CLI
- Allowed to use AI & Google
