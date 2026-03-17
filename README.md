# simple-books-api-tests

A REST API test collection built with Postman, covering order management endpoints of the [Simple Books API](https://simple-books-api.click).

Created by **Oscar** as part of API testing practice.🚀

---

## Test coverage

### `POST /orders`
| # | Scenario | Expected status |
|---|----------|----------------|
| 01 | Happy path | 201 |
| 02 | Missing customerName | 400 |
| 03 | Wrong data type (bookId as boolean) | 400 |
| 04 | Empty body | 400 |
| 05 | No authorization token | 401 |
| 06 | Invalid token | 401 |
| 07 | Data verification (POST → GET) | 201 / 200 |

### `PATCH /orders/:orderId`
| # | Scenario | Expected status |
|---|----------|----------------|
| 09 | Update customerName | 204 |
| — | Verify update via GET | 200 |

### `DELETE /orders/:orderId`
| # | Scenario | Expected status |
|---|----------|----------------|
| 10 | Delete order | 204 |
| — | Verify deletion via GET | 404 |

### Other
| Endpoint | Scenario | Expected status |
|----------|----------|----------------|
| `GET /status` | API health check | 200 |

---

## Setup

### 1. Import the collection

In Postman: **Import** → select `Simple_Book_API_postman_collection.json`

### 2. Set the base URL

In collection variables, set `baseUrl` to:
```
https://simple-books-api.click
```

### 3. Register your API client

Open `Create a token / Register API Client` and send the request.  
The `accessToken` is saved automatically to collection variables — no manual setup needed.

> ℹ️ The token is valid for 7 days. Re-run this request when it expires.

### 4. Run the collection

**Option A — Manual:** Run requests one by one, top to bottom.

**Option B — Collection Runner:** Three dots next to collection name → **Run collection** → see full pass/fail report.

> ⚠️ Run requests in order — later tests depend on `orderId` saved by request 01.

---

## Project structure

```
📁 simple-books-api-tests
  📄 README.md
  📄 Simple_Book_API_postman_collection.json
```

---

## Tech

- [Postman](https://www.postman.com/)
- [Simple Books API](https://simple-books-api.click)
- JavaScript (Postman test scripts)
