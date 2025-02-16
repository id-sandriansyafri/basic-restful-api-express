# 📌 User API Documentation

## 🔹 Register User

📍 **Endpoint:** `POST /api/users`

📄 **Description:**

Registers a new user in the system.

📥 **Request Body (JSON):**

```json
{
  "name": "John Doe",
  "email": "johndoe@example.com",
  "password": "securepassword"
}
```

📤 **Response (JSON):**

✅ **Success (201 Created)**

```json
{
  "message": "User registered successfully",
  "data": {
    "id": 1,
    "name": "John Doe",
    "email": "johndoe@example.com"
  }
}
```

❌ **Error (400 Bad Request)**

```json
{
  "error": "Email already exists"
}
```

---

## 🔹 Login User

📍 **Endpoint:** `POST /api/auth/login`

📄 **Description:**

Authenticates a user and returns a token.

📥 **Request Body (JSON):**

```json
{
  "username": "pzn",
  "password": "securepassword"
}
```

📤 **Response (JSON):**

✅ **Success (200 OK)**

```json
{
  "message": "Login successful",
  "token": "your_jwt_token_here"
}
```

❌ **Error (401 Unauthorized)**

```json
{
  "error": "Invalid credentials"
}
```

---

## 🔹 Get User Profile

📍 **Endpoint:** `GET /api/users/me`

🔑 **Authorization:** Bearer Token

📄 **Description:**

Fetches the authenticated user's profile.

📥 **Headers:**

```
Authorization: Bearer your_jwt_token_here
```

📤 **Response (JSON):**

✅ **Success (200 OK)**

```json
{
  "id": 1,
  "name": "John Doe",
  "email": "johndoe@example.com"
}
```

❌ **Error (401 Unauthorized)**

```json
{
  "error": "Token expired or invalid"
}
```

---

### 🔹 **Update User Profile (MySQL + API)**

📍 **Endpoint:** `PUT /api/users/me`

🔑 **Authorization:** Bearer Token

📄 **Description:**

Memperbarui profil user yang sedang login.

📥 **Headers:**

```
Authorization: Bearer your_jwt_token_here
Content-Type: application/json
```

📥 **Request Body (JSON):**

```json
{
  "name": "John Doe Updated",
  "email": "johnupdated@example.com",
  "password": "newsecurepassword"
}
```

📤 **Response (JSON):**

✅ **Success (200 OK)**

```json
{
  "message": "Profile updated successfully",
  "data": {
    "id": 1,
    "name": "John Doe Updated",
    "email": "johnupdated@example.com"
  }
}
```

❌ **Error (400 Bad Request)**

```json
{
  "error": "Invalid email format"
}
```

❌ **Error (401 Unauthorized)**

```json
{
  "error": "Token expired or invalid"
}
```

## 🔹 **Logout ser**

📍 **Endpoint:** `POST /api/auth/logout`

🔑 **Authorization:** Bearer Token

📄 **Description:**

Menghapus sesi login user dengan cara meng-*invalidate* token.

📥 **Headers:**

```
Authorization: Bearer your_jwt_token_here
Content-Type: application/json
```

📤 **Response (JSON):**

✅ **Success (200 OK)**

```json
{
  "message": "Logout successful"
}
```

❌ **Error (401 Unauthorized)**

```json
{
  "error": "Token expired or invalid"
}
```

💡 **Catatan:**

- Gunakan **JWT Token** untuk mengakses endpoint yang membutuhkan autentikasi.
- Pastikan semua request dikirim dengan **Content-Type: application/json**.

---

🚀 **Siap untuk digunakan di Notion!**

Silakan salin dan tempel ke Notion untuk dokumentasi API yang rapi & mudah dibaca! 😊