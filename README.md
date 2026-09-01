# 📚 Books CRUD API

<p align="center"><strong>REST API for managing books with Node.js, Express, MongoDB and Mongoose.</strong></p>

## Overview

This repository implements create, read, update and delete operations for books. It is a compact learning project for Express routing, MongoDB persistence and Mongoose models.

The current dependency versions are historical. Production use requires upgrades, configuration management, validation, structured errors, security controls and automated tests.

## Technology Stack

| Layer | Technology |
|---|---|
| Runtime | Node.js |
| Framework | Express 4 |
| Database | MongoDB |
| Object modelling | Mongoose 5 |
| Request parsing | body-parser |
| Modules | CommonJS |

## Available Endpoints

| Method | Path | Purpose |
|---|---|---|
| GET | / | Basic service response |
| GET | /books | List books |
| GET | /books/:id | Fetch one book |
| POST | /books | Create a book |
| PUT | /books/:id | Update or upsert a book |
| DELETE | /books/:id | Delete a book |

## Project Structure

\`\`\`text
CURD-APP-Assignment/
├── app.js              # Database connection and HTTP server
├── models/
│   └── book.js         # Book schema
├── routes/
│   └── books.js        # CRUD routes
├── package.json
├── README.md
└── LICENSE
\`\`\`

## Architecture

\`\`\`text
API client
   │ HTTP + JSON
   ▼
Express application
   │
   ▼
Books router
   │
   ▼
Mongoose
   │
   ▼
MongoDB example database
\`\`\`

## Complete Local Setup

### Prerequisites

- Git
- Node.js
- npm
- MongoDB Community Server or a compatible development database

Use an isolated environment because the baseline dependencies are old.

### Clone and install

\`\`\`bash
git clone https://github.com/deepakvish001/CURD-APP-Assignment.git
cd CURD-APP-Assignment
npm install
\`\`\`

### Start MongoDB

Start MongoDB using the command appropriate for your operating system. The current application connects to:

\`\`\`text
mongodb://localhost/example
\`\`\`

MongoDB can create the database and books collection on first write. Manual creation is optional.

### Start the API

\`\`\`bash
node app.js
\`\`\`

The server listens at:

\`\`\`text
http://localhost:8080
\`\`\`

## Example Requests

Create a book:

\`\`\`bash
curl -X POST http://localhost:8080/books \
  -H "Content-Type: application/json" \
  -d '{"title":"Clean Code","author":"Robert C. Martin","category":"Software Engineering"}'
\`\`\`

List all books:

\`\`\`bash
curl http://localhost:8080/books
\`\`\`

Fetch one book:

\`\`\`bash
curl http://localhost:8080/books/BOOK_ID
\`\`\`

Update a book:

\`\`\`bash
curl -X PUT http://localhost:8080/books/BOOK_ID \
  -H "Content-Type: application/json" \
  -d '{"title":"Updated Title","author":"Updated Author","category":"Technology"}'
\`\`\`

Delete a book:

\`\`\`bash
curl -X DELETE http://localhost:8080/books/BOOK_ID
\`\`\`

## Current Book Model

| Field | Type | Validation |
|---|---|---|
| title | String | None |
| author | String | None |
| category | String | None |

A production model should add required values, trimming, length limits, timestamps, indexes and safe update rules.

## Known Limitations

- Database URL and port are hard coded.
- Connection failures are not handled.
- The server starts before database readiness.
- Input validation is absent.
- Invalid identifiers are not handled consistently.
- Several error paths return HTTP 200.
- Documents and errors are logged directly.
- List queries are unbounded.
- PUT performs an unexpected upsert.
- Authentication and authorisation are absent.
- CORS, security headers and rate limits are absent.
- Automated tests are absent.
- Dependencies are outdated.
- Graceful shutdown is absent.

## Security Requirements

Before public deployment:

- upgrade maintained dependencies
- validate and normalise requests
- use environment-based secrets
- return consistent status codes
- add security headers and a deliberate CORS policy
- rate-limit public endpoints
- prevent unsafe query injection
- add authentication and role checks where needed
- avoid logging request bodies or personal information
- run dependency and deployment security checks

## Testing Roadmap

Add coverage for:

- model validation
- create, list, detail, update and delete
- malformed JSON
- missing and invalid fields
- invalid MongoDB identifiers
- not-found responses
- database errors and timeouts
- pagination, filtering and sorting
- authentication and permissions
- rate limiting
- graceful startup and shutdown
- API contract compatibility

## Modernisation Roadmap

- Correct the project name from CURD to CRUD
- Upgrade Node.js, Express and Mongoose
- Add environment configuration
- Add database lifecycle management
- Introduce controllers, services and repositories
- Add request validation and error middleware
- Add pagination, filters and sorting
- Add ISBN and publication metadata
- Add users, roles and authentication
- Add borrowing and inventory workflows
- Add OpenAPI documentation
- Add automated tests and CI
- Add Docker development support
- Add deployment and observability guidance

## Contributing

Keep each pull request limited to one independently verifiable change.

\`\`\`bash
git checkout master
git pull --ff-only
git checkout -b feat/short-change-name
npm install
git add .
git commit -m "feat: describe the change"
git push -u origin feat/short-change-name
\`\`\`

## License

See [LICENSE](LICENSE).

---

<p align="center">A compact foundation for learning Express, Mongoose and MongoDB.</p>
