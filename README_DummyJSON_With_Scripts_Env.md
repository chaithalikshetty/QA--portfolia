# DummyJSON API Testing - Postman Collection

This folder contains a Postman collection and environment for API testing using **DummyJSON** (used as an alternative when ReqRes POSTs are blocked).

---

## 📂 Contents
- `DummyJSON_API_Testing.postman_collection.json` — Postman collection with CRUD requests and test scripts.  
- `DummyJSON_API_Environment.postman_environment.json` — Environment file with `baseUrl` and `userId` variables.  
- `DummyJSON_API_TestCases.xlsx` — Manual test cases document for the endpoints in this collection.

---

## ⚙️ How to use
1. Open **Postman → Import → File** → select `DummyJSON_API_Testing.postman_collection.json` and import.  
2. Import the environment file `DummyJSON_API_Environment.postman_environment.json` and select it from the top-right environment dropdown.  
3. Open the collection and run requests (Create User → Update → Patch → Delete).  
4. Use the Test Runner to execute collection with the selected environment. Results and assertions are included in the collection's test scripts.

---

## 🌐 About Environment File
The environment file helps manage variables like the base API URL and user IDs dynamically.  
By using environment variables (`{{baseUrl}}`, `{{userId}}`), you can:
- Reuse the same requests for different environments or user IDs.  
- Avoid hardcoding values directly inside each request.  
- Make scripts and assertions automatically adapt to variable values.

Example:  
`GET {{baseUrl}}/users/{{userId}}` → becomes `GET https://dummyjson.com/users/1` when environment is selected.

---

## 🧠 About Scripts
Each request contains small **JavaScript-based test scripts** written under Postman’s *Tests* tab.  
These automatically validate:
- Response status codes (e.g., 200, 201, 204).  
- Presence of specific keys (like `id`, `users`, etc.).  
- Matching environment variable values (`userId` consistency).

After execution, results appear under the **“Test Results”** section in Postman.  
This helps confirm that each API behaves as expected without manual checking.

---

## 🔗 Endpoints Covered
- `GET {{baseUrl}}/users`  
- `GET {{baseUrl}}/users/{{userId}}`  
- `POST {{baseUrl}}/users/add`  
- `PUT {{baseUrl}}/users/{{userId}}`  
- `PATCH {{baseUrl}}/users/{{userId}}`  
- `DELETE {{baseUrl}}/users/{{userId}}`

---

## 📝 Notes
- DummyJSON returns `200` for creation (`/users/add`) and supports full CRUD operations for demo/testing.  
- You can change the `userId` in the environment file to test different users.  
- Scripts are included in each request to validate responses automatically.

---

Generated for your GitHub portfolio. You can upload the entire folder `dummyjson_api_docs` to your repository.
