# API Testing Repository

## Overview
This repository contains Postman collections and scripts designed to test the functionality of a Library API. The scripts demonstrate core API testing practices, including creating, retrieving, and deleting books, while integrating assertions and variable management.

## Key Features
- **Postman Tests**: Includes requests for adding, retrieving, and deleting books.
- **Dynamic Variables**: Uses Postman variables for dynamic data (e.g., `isbn`, `author`, and `book`).
- **Assertions**:
  - Validate response status codes.
  - Check response headers and content.
  - Confirm JSON schema compliance.
  - Test logical conditions and data integrity.
- **Error Handling**: Implements clean-up logic for failed test scenarios.

## Newman Integration
Use Newman, Postman’s command-line tool, to run the collection and generate detailed reports. Below are examples of common Newman commands:

### Running the Collection
```bash
newman run Library_API.postman_collection.json -e environment.json
```

### Generating an HTML Report
```bash
newman run Library_API.postman_collection.json -e environment.json -r html --reporter-html-export report.html
```

### Generating a JSON Report
```bash
newman run Library_API.postman_collection.json -e environment.json -r json --reporter-json-export report.json
```

## How to Use
1. **Import the Collection**: Open Postman and import the `Library_API.postman_collection.json` file.
2. **Set Up Environment**: Configure the required environment variables such as `base_url`, `isbn`, and `author`.
3. **Run Requests**: Execute individual requests or the entire collection to validate API functionality.
4. **Automate with Newman**: Use the Newman commands to run tests in CI/CD pipelines or locally.

## Collection Structure
1. **Addbook**: Adds a new book to the library.
   - Validates response status, message, and generated book ID.
   - Cleans up existing data if duplicate entries are detected.
2. **Get Book for ID**: Retrieves book details by ID.
   - Validates the returned author matches the expected value.
3. **Delete Book**: Deletes a book by ID.
   - Validates response status and ensures the book is successfully removed.

## Prerequisites
- [Postman](https://www.postman.com/downloads/)
- [Newman](https://www.npmjs.com/package/newman): Install using `npm install -g newman`
- Node.js (for running Newman)

---
This repository showcases essential API testing techniques for quick reference during interviews or hands-on demonstrations.
