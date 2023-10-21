# RENDER LINK: https://week19-node-api-docs-and-deploy.onrender.com
# AUTHORS API Documentation
Here's the updated documentation for the Author API routes:
- **MainRoute**: `api/owners/`

## Owner API Documentation

This documentation provides details about the API endpoints for managing owners.

### Owner Sign Up

```
POST /signup
```

Sign up a new owner.

#### Request Body

```json
{
  "name": "John Doe",
  "email": "johndoe@example.com",
  "password": "password123"
}
```

#### Response

- `201 Created` on success

```json
{
  "message": "Owner created successfully",
  "owner": {
    "id": 1,
    "name": "John Doe",
    "email": "johndoe@example.com"
  }
}
```

Note: If the owner already exists, a `409 Conflict` response will be returned.

### Owner Login

```
POST /login
```

Log in an owner.

#### Request Body

```json
{
  "email": "johndoe@example.com",
  "password": "password123"
}
```

#### Response

- `200 OK` on success

```json
{
  "message": "Owner logged in successfully",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJqb2huZG9lQGV4YW1wbGUuY29tIiwiaWF0IjoxNjM0MjY0Mzg1LCJleHAiOjE2MzQyNjgxODV9.RCJpS5oVWxQ5w3LmJd1P0iLq5zW0B7rV0WUVvVH3jwY"
}
```

Note: If the owner is not found or the credentials are invalid, a `404 Not Found` or `401 Unauthorized` response will be returned, respectively.

Please note that the actual token value will be different in each response.

## Get All Authors

- **Route**: `/`
- **Method**: GET

Retrieves all authors.

### Response

If there are authors available:

- **Status**: 200 OK
- **Content**: JSON array containing all authors.

If there are no authors available:

- **Status**: 404 Not Found
- **Content**: JSON object with an "error" property set to "No authors found."

## Get a Single Author by ID

- **Route**: `/:id`
- **Method**: GET

Retrieves a specific author by their ID.

### Response

If the author exists:

- **Status**: 200 OK
- **Content**: JSON object representing the author.

If the author does not exist:

- **Status**: 404 Not Found
- **Content**: JSON object with an "error" property set to "Author Not Found."

## Create a New Author

- **Route**: `/`
- **Method**: POST

Creates a new author with the provided authorName.

### Request Body

- **authorName**: Name of the author.

### Response

If the author is successfully created:

- **Status**: 200 OK
- **Content**: JSON object with a "message" property set to "Author created successfully" and a "createAuthor" property containing the details of the created author.

If the creation fails:

- **Status**: 404 Not Found
- **Content**: JSON object with a "status" property set to "Author Not Created."

## Update an Author

- **Route**: `/:id`
- **Method**: PUT

Updates an existing author with the provided ID and authorName.

### Request Body

- **authorName**: Updated name of the author.

### Response

If the author is successfully updated:

- **Status**: 200 OK
- **Content**: JSON object with a "message" property set to "Author updated successfully" and an "updateAuthor" property containing the details of the updated author.

If the update fails or the author does not exist:

- **Status**: 404 Not Found
- **Content**: JSON object with a "status" property set to "Author Not Found."

## Delete an Author

- **Route**: `/:id`
- **Method**: DELETE

Deletes an existing author with the provided ID.

### Response

If the author is successfully deleted:

- **Status**: 200 OK
- **Content**: JSON object with a "message" property set to "Author Deleted successfully" and a "deleteAuthor" property containing the details of the deleted author.

If the deletion fails or the author does not exist:

- **Status**: 404 Not Found
- **Content**: JSON object with a "status" property set to "Author Not Found."




# BOOKS API DOCUMENTATION

## Get All Books
- **MainRoute**: `/api/books`
- **Route**: `/`
- **Method**: GET

Retrieves all books.

### Response

If there are books available:

- **Status**: 200 OK
- **Content**: JSON array containing all books.

If there are no books available:

- **Status**: 404 Not Found
- **Content**: JSON object with an "error" property set to "No Books found."

## Get a Single Book by ID

- **Route**: `/:id`
- **Method**: GET

Retrieves a specific book by its ID.

### Response

If the book exists:

- **Status**: 200 OK
- **Content**: JSON object representing the book.

If the book does not exist:

- **Status**: 404 Not Found
- **Content**: JSON object with an "error" property set to "Book Not Found."

## Create a New Book

- **Route**: `/`
- **Method**: POST

Creates a new book with the provided details.

### Request Body

- **title**: Title of the book.
- **authorId**: ID of the author.
- **price**: Price of the book.
- **bookStoreId**: ID of the bookstore.
- **image**: Image URL of the book.

### Response

If the book is successfully created:

- **Status**: 200 OK
- **Content**: JSON object with a "message" property set to "New Book created successfully" and a "createBook" property containing the details of the created book.

If the creation fails:

- **Status**: 404 Not Found
- **Content**: JSON object with a "status" property set to "Book Not Created."

## Update a Book

- **Route**: `/:id`
- **Method**: PUT

Updates an existing book with the provided ID.

### Request Body

- **title**: Updated title of the book.
- **authorId**: Updated ID of the author.
- **price**: Updated price of the book.
- **bookStoreId**: Updated ID of the bookstore.
- **image**: Updated image URL of the book.

### Response

If the book is successfully updated:

- **Status**: 200 OK
- **Content**: JSON object with a "message" property set to "Book updated successfully" and an "updateBook" property containing the details of the updated book.

If the update fails:

- **Status**: 404 Not Found
- **Content**: JSON object with a "status" property set to "Book Not Found."

## Delete a Book

- **Route**: `/:id`
- **Method**: DELETE

Deletes an existing book with the provided ID.

### Response

If the book is successfully deleted:

- **Status**: 200 OK
- **Content**: JSON object with a "message" property set to "Book deleted successfully" and a "deleteBook" property containing the details of the deleted book.

If the deletion fails or the book does not exist:

- **Status**: 404 Not Found
- **Content**: JSON object with a "status" property set to "Book Not Found."




# BOOKSTORE API DOCUMENTATION

Here's the updated documentation for the BookStore API routes:

## Get All BookStores

- **Route**: `/`
- **Method**: GET

Retrieves all BookStores.

### Response

If there are BookStores available:

- **Status**: 200 OK
- **Content**: JSON array containing all BookStores.

If there are no BookStores available:

- **Status**: 404 Not Found
- **Content**: JSON object with an "error" property set to "No BookStores found."

## Get a Single BookStore by ID

- **Route**: `/:id`
- **Method**: GET

Retrieves a specific BookStore by its ID.

### Response

If the BookStore exists:

- **Status**: 200 OK
- **Content**: JSON object representing the BookStore.

If the BookStore does not exist:

- **Status**: 404 Not Found
- **Content**: JSON object with an "error" property set to "No BookStores found."

## Create a New BookStore

- **Route**: `/`
- **Method**: POST

Creates a new BookStore with the provided name and location.

### Request Body

- **name**: Name of the BookStore.
- **location**: Location of the BookStore.

### Response

If the BookStore is successfully created:

- **Status**: 200 OK
- **Content**: JSON object with a "message" property set to "New Book Store created successfully" and a "createBookStore" property containing the details of the created BookStore.

If the creation fails:

- **Status**: 404 Not Found
- **Content**: JSON object with a "status" property set to "Book Store Not Created."

## Update a BookStore

- **Route**: `/:id`
- **Method**: PUT

Updates an existing BookStore with the provided ID, name, and location.

### Request Body

- **name**: Updated name of the BookStore.
- **location**: Updated location of the BookStore.

### Response

If the BookStore is successfully updated:

- **Status**: 200 OK
- **Content**: JSON object with a "message" property set to "Book Store updated successfully" and an "updateBookStore" property containing the details of the updated BookStore.

If the update fails:

- **Status**: 404 Not Found
- **Content**: JSON object with a "status" property set to "Book Store Not Updated."

## Delete a BookStore

- **Route**: `/:id`
- **Method**: DELETE

Deletes an existing BookStore with the provided ID.

### Response

If the BookStore is successfully deleted:

- **Status**: 200 OK
- **Content**: JSON object with a "message" property set to "Book Store Deleted successfully" and a "deleteBookStore" property containing the details of the deleted BookStore.

If the deletion fails or the BookStore does not exist:

- **Status**: 404 Not Found
- **Content**: JSON object with a "status" property set to "Book Store Not Deleted."
