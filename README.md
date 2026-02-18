<!--
THEME: “Calm Systems, Sharp Edges”
Palette: dark-friendly, minimal, one accent color.
Goal: make visitors understand your architecture taste in 15 seconds.
-->

<h1 align="center">Hi, I'm Bahadır 👋</h1>
<p align="center">
  I build <b>boring-in-production</b> backend systems: secure, observable, and scalable.
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/YOUR-LINKEDIN/">LinkedIn</a> •
  <a href="https://YOUR-PORTFOLIO/">Portfolio</a> •
  <a href="mailto:YOUR@MAIL.COM">Email</a>
</p>

---

## ⚙️ What I work on
- **.NET backend engineering** (API / Application / Domain / Infrastructure)
- **Microservices + Gateways** (routing, rate limiting, auth forwarding)
- **Auth** (JWT, refresh-token rotation, OTP-first flows)
- **Data pipelines** (CDC with Debezium + Kafka → audit/event store in MongoDB)
- **SQL Server** (stored procedures, ADO.NET mapping patterns)

---

## 🧠 Current obsessions
- Making distributed systems *predictable*: idempotency, retries, dead-letter strategies  
- Auditability as a feature: event timelines, diff views, traceable operations  
- Clean contracts: stable DTOs, clear error models, consistent naming  

---

## 🧩 Featured projects (pin these)
### 1) Audit Pipeline (CDC → Kafka → Mongo)
**Why:** production-grade audit trail with idempotent ingestion  
**Highlights:** Debezium connector, Kafka consumer worker, unique offset index, timeline viewer

### 2) API Gateway (YARP)
**Why:** a single secure entry point  
**Highlights:** centralized JWT verification, token forwarding, rate limiting, health checks

### 3) Mongo Data Provider Library
**Why:** reusable foundation across services  
**Highlights:** cached client/db, named connections, DI-first design, optional health checks

> If any project is private, publish a “public mirror” repo with architecture docs + diagrams.

---

## 🧭 Architecture snapshot
```mermaid
flowchart LR
  A[Clients] --> G[API Gateway]
  G --> S1[Service A (.NET)]
  G --> S2[Service B (.NET)]
  S1 --> M[(SQL Server)]
  M --> D[Debezium]
  D --> K[(Kafka)]
  K --> C[Audit Consumer]
  C --> O[(MongoDB)]
  O --> V[Audit Viewer UI]
