# Domain terminology and model

**Guide ID:** 003  
**Category:** architecture  
**Project:** Books CRUD API

## Objective

Standardise core entities, states, relationships and invariants.

## Project Context

Books CRUD API serves API consumers, librarians, administrators and backend maintainers. Apply this guidance to book records, validation, searching, pagination, inventory, borrowing workflows and MongoDB persistence.

## Engineering Guidance

1. Define the user or operational outcome and a measurable completion signal.
2. Document entities, validation, permissions, dependencies and failure states.
3. Keep domain rules separate from presentation, persistence and infrastructure.
4. Preserve existing behaviour and data or provide migration and rollback steps.
5. Handle success, empty, invalid, denied, conflict and system-error states.
6. Add diagnostics without exposing secrets or sensitive user information.
7. Document security, compatibility and operational trade-offs.

Treat HTTP semantics, schema validation, database connection lifecycle, query limits and personal-data minimisation as first-class concerns.

## Acceptance Criteria

- Affected roles and intended outcome are explicit.
- Data and validation constraints are documented.
- Permission checks occur at a trusted boundary.
- Existing consumers remain compatible or receive a migration path.
- High-risk success and failure paths have verification.
- Privacy and security risks have mitigations.
- Deployment and rollback expectations are clear.

## Verification

Review the documentation against app.js, models/book.js, routes/books.js and package.json. For implementation changes, run the API and exercise relevant endpoints against an isolated MongoDB database.

## Review Scope

Keep implementation limited to this topic. Submit unrelated refactors, dependency upgrades and formatting changes separately.
