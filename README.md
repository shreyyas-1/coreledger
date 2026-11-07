# CoreLedger

A mini core banking backend built with Java and Spring Boot.

## Why I'm building this

Every night, banks run a batch job that calculates interest for every account. That job has to handle lakhs of accounts, recover if it crashes halfway, never credit anyone twice, and keep every paisa exact.

Banks also keep an audit log of every change to their data, and that log should not be editable, even by someone with direct database access.

CoreLedger is my attempt at building a small version of both.

## Planned features

- [ ] Account and fund-transfer APIs using BigDecimal for exact money handling and idempotent requests to prevent duplicate transfers
- [ ] Nightly interest calculation for 1,00,000+ simulated accounts using Spring Batch
- [ ] Restart from the last completed chunk if the job fails, and a unique (account, date) constraint so interest is never credited twice
- [ ] Tamper-evident audit log using SHA-256 hash chaining, where editing any past entry breaks the chain
- [ ] Role-based access for Customer, Teller and Auditor using Spring Security and JWT

## Tech stack

Java, Spring Boot, Spring Batch, Spring Security, MySQL, Docker

## Roadmap

1. Account and transfer APIs
2. Safe transfers with transactions and idempotency
3. Nightly interest batch job
4. Restart handling, re-run safety and performance tuning
5. Hash-chained audit log with a verify endpoint
6. Authentication, Docker setup and deployment

## Status

Work in progress. I'll tick off features above as they are completed.
