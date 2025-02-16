# 📞 Contact API Specification

# 🆕 **Create Contact API**

📍 **Endpoint:** `POST /api/contacts`

🔑 **Headers:**

- `Authorization: token`

📥 **Request Body:**

```json
{
  "first_name": "Sandrian",
  "last_name": "Syafri",
  "email": "sandrian@example",
  "phone": "1234567890"
}
```

📤 **Response Body (Success ✅):**

```json
{
  "data": {
    "id": 1,
    "first_name": "Sandrian",
    "last_name": "Syafri",
    "email": "sandrian@example",
    "phone": "1234567890"
  }
}
```

❌ **Response Body (Error):**

```json
{
  "errors": "Email is not valid format"
}
```

---

## ✏️ **Update Contact API**

📍 **Endpoint:** `PUT /api/contacts/:id`

🔑 **Headers:**

- `Authorization: token`

📥 **Request Body:**

```json
{
  "first_name": "Sandrian",
  "last_name": "Syafri",
  "email": "sandrian@example",
  "phone": "1234567890"
}
```

📤 **Response Body (Success ✅):**

```json
{
  "data": {
    "id": 1,
    "first_name": "Sandrian",
    "last_name": "Syafri",
    "email": "sandrian@example",
    "phone": "1234567890"
  }

```

❌ **Response Body (Error):**

```json
{
  "errors": "Email is not valid format"
}
```

---

## 🔍 **Get Contact API**

📍 **Endpoint:** `GET /api/contacts/:id`

🔑 **Headers:**

- `Authorization: token`

📤 **Response Body (Success ✅):**

```json
{
  "data": {
    "id": 1,
    "first_name": "Sandrian",
    "last_name": "Syafri",
    "email": "sandrian@example",
    "phone": "1234567890"
  }
}
```

❌ **Response Body (Error):**

```json
{
  "errors": "Contact is not found"
}
```

---

## 🔎 **Search Contact API**

📍 **Endpoint:** `GET /api/contacts`

🔑 **Headers:**

- `Authorization: token`

📌 **Query Params:**

- `name` → Search by `first_name` or `last_name` (optional, `LIKE`)
- `email` → Search by email (optional, `LIKE`)
- `phone` → Search by phone (optional, `LIKE`)
- `page` → Number of page (default: `1`)
- `size` → Items per page (default: `10`)

📤 **Response Body (Success ✅):**

```json
{
  "data": [
    {
      "id": 1,
      "first_name": "Sandrian",
      "last_name": "Syafri",
      "email": "sandrian@example",
      "phone": "1234567890"
    },
    {
      "id": 2,
      "first_name": "Sandrian",
      "last_name": "Aja",
      "email": "sandrian@aja.com",
      "phone": "2345678901"
    }
  ],
  "paging": {
    "page": 1,
    "total_page": 3,
    "total_item": 1
  }
}

```

---

## 🗑️ **Remove Contact API**

📍 **Endpoint:** `DELETE /api/contacts/:id`

🔑 **Headers:**

- `Authorization: token`

📤 **Response Body (Success ✅):**

```json
{
  "data": "OK"
}
```

❌ **Response Body (Error):**

```json
{
  "errors": "Contact is not found"
}
```