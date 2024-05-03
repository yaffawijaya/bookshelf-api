# Basic - Bookshelf API using Hapi

This API allows you to manage a collection of books. You can perform operations such as adding, retrieving, updating, and deleting books.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Endpoints](#endpoints)
  - [Add a Book](#add-a-book)
  - [Get All Books](#get-all-books)
  - [Get a Book by ID](#get-a-book-by-id)
  - [Update a Book by ID](#update-a-book-by-id)
  - [Delete a Book by ID](#delete-a-book-by-id)
- [Response Format](#response-format)
- [Examples](#examples)

## Prerequisites

- Node.js installed on your machine
- npm or yarn package manager installed
- Basic understanding of RESTful APIs

## Getting Started

1. Clone this repository.
2. Install dependencies by running `npm install`.
3. Start the server by running `npm start`.

## Endpoints

### Add a Book

- **URL:** `/books`
- **Method:** `POST`
- **Description:** Adds a new book to the collection.
- **Request Body:**
  - `name` (string, required): Name of the book.
  - `year` (number): Year of publication.
  - `author` (string): Author of the book.
  - `summary` (string): Summary of the book.
  - `publisher` (string): Publisher of the book.
  - `pageCount` (number): Total number of pages in the book.
  - `readPage` (number): Number of pages already read.
  - `reading` (boolean): Indicates whether the book is currently being read.

### Get All Books

- **URL:** `/books`
- **Method:** `GET`
- **Description:** Retrieves all books or filtered books based on query parameters.
- **Query Parameters:**
  - `name` (string): Filter books by name.
  - `reading` (boolean): Filter books by reading status (0 for not reading, 1 for reading).
  - `finished` (boolean): Filter books by finished status (0 for unfinished, 1 for finished).

### Get a Book by ID

- **URL:** `/books/{bookId}`
- **Method:** `GET`
- **Description:** Retrieves a specific book by its ID.

### Update a Book by ID

- **URL:** `/books/{bookId}`
- **Method:** `PUT`
- **Description:** Updates the details of a specific book.
- **Request Body:** Same as adding a book.

### Delete a Book by ID

- **URL:** `/books/{bookId}`
- **Method:** `DELETE`
- **Description:** Deletes a specific book from the collection.

## Response Format

All responses follow a standardized format:

- `status` (string): Indicates the status of the request (`success` or `fail`).
- `message` (string): Descriptive message about the request status.
- `data` (object): Contains the relevant data returned by the API (if applicable).

## Examples

### Add a Book

```http
POST /books
Content-Type: application/json

{
  "name": "Sample Book",
  "year": 2022,
  "author": "John Doe",
  "summary": "Lorem ipsum dolor sit amet...",
  "publisher": "Publisher XYZ",
  "pageCount": 300,
  "readPage": 150,
  "reading": true
}
