# 🧪 AutomationExercise API Test Collection

This repository contains a comprehensive Postman test collection for the [AutomationExercise](https://automationexercise.com/api_list) public APIs. It automates the testing of core endpoints such as product listing, account creation, deletion, and user data retrieval.

---

## Project Contents

This Postman collection includes tests for the following endpoints:

| Endpoint                           | Method | Description                         |
|------------------------------------|--------|-------------------------------------|
| `/api/productsList`               | GET    | Retrieve all products               |
| `/api/brandsList`                 | GET    | Retrieve all brands                 |
| `/api/searchProduct`             | POST   | Search for a specific product       |
| `/api/createAccount`             | POST   | Create a new user account           |
| `/api/deleteAccount`             | DELETE | Delete an existing user account     |
| `/api/updateAccount`             | PUT    | Update user information             |
| `/api/getUserDetailByEmail`      | GET    | Get user details by email address   |

---

## How to Use

1. **Clone or Download** this repository.

2. **Import into Postman:**
   - Open Postman.
   - Click **Import → Raw Text** or **Upload File**.
   - Paste or upload the provided Postman Collection JSON.

3. **Run Collection:**
   - Use the **Collection Runner** or **Newman CLI** to run all requests with built-in tests.

---

## Tests Included

Each request has tests such as:

- `Status code should be 200 OK`
- `Response should contain expected keys (e.g., 'products', 'brands', 'user')`
- `User creation and deletion success messages`
- `Array and object validations`

Example from `Get All Products` test:
```javascript
pm.test("Should return 200 OK", () => pm.response.to.have.status(200));
const res = pm.response.json();
pm.test("Should include a list of products", () => pm.expect(res.products).to.be.an('array'));
