# Enterprise Double-Entry Financial Ledger API

A production-ready, ACID-compliant financial backend engine built with **FastAPI**, **Async SQLAlchemy**, and **PostgreSQL**.

## 🚀 Architectural Key Features

- **Double-Entry Bookkeeping:** Immutable `DEBIT` and `CREDIT` ledger records for strict auditability and zero balance discrepancies.
- **Concurrency & Race Condition Safety:** Row-level pessimistic locking (`SELECT ... FOR UPDATE`) prevents concurrent balance modification bugs.
- **Deadlock Mitigation:** Deterministic row-locking order utilizing sorted UUIDs to prevent database lock contention under load.
- **Idempotency Safeguard:** Custom `X-Idempotency-Key` header tracking to block duplicate transactions and double-charges.
- **High-Throughput Async Engine:** Optimized connection pooling with `asyncpg` for minimal latency.

## 🛠 Tech Stack

- **Framework:** FastAPI
- **Database Engine:** PostgreSQL
- **ORM:** SQLAlchemy 2.0 (Async Engine)
- **Database Driver:** `asyncpg`
- **Validation:** Pydantic v2
