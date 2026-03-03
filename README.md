# Strategic Plan Monitoring System (Proof of Concept)

## Overview

The Strategic Plan Monitoring System is a workflow-driven monitoring platform developed as a Proof of Concept (PoC) to demonstrate how structured governance and performance tracking can be digitized using modular backend architecture and event-driven communication.

The system supports hierarchical planning structures, progress tracking, evidence submission, and workflow-based approvals.

> Note: Source code is not publicly available due to confidentiality. This repository documents the architecture, design principles, and technical implementation approach.

---

## Problem Statement

Traditional governance and monitoring systems often face:

- Manual tracking processes
- Limited visibility into approval stages
- Poor audit traceability
- Tight coupling between system modules
- Limited scalability

This project demonstrates how modular backend services, workflow orchestration, and asynchronous messaging can address these challenges.

---

## High-Level Architecture

![System Architecture](./images/architecture.png)

### Core Components

- **Backend Service (Spring Boot)**  
  Handles REST APIs, business logic, and data persistence.

- **Workflow Engine (Camunda 8)**  
  Manages approval processes and state transitions.

- **Event Communication (Apache Kafka)**  
  Enables asynchronous notifications and system decoupling.

- **Authentication & Authorization (OAuth2 / OIDC via Keycloak)**  
  Provides role-based access control.

- **Frontend (Angular)**  
  Implements workflow interfaces and dashboards.

- **Database (MySQL)**  
  Stores structured domain and workflow-related data.

- **Containerization (Docker)**  
  Ensures consistent deployment environments.

---

## System Workflow

![Workflow Sequence](./images/Diagrams-Sequence.drawio.png)

### High-Level Flow

1. User submits strategic plan data via Angular frontend.
2. Backend validates and persists domain entities.
3. Workflow engine initiates approval process.
4. Kafka events trigger asynchronous notifications.
5. Role-based users complete assigned workflow tasks.
6. Final approval updates system state and audit logs.

---

## Backend Architecture Design

### Design Principles

- Layered architecture (Controller → Service → Repository)
- Clear domain boundaries
- DTO-based API contracts
- Separation between domain data and workflow state
- Event-driven communication for decoupling

---

## Event-Driven Communication Model

Kafka is used to:

- Publish workflow state changes
- Trigger notification processing
- Decouple core domain logic from auxiliary services
- Improve scalability and extensibility

---

## Data Model Overview

![Entity Relationship Diagram](./images/ERD.png)

The relational model supports:

- Strategic plan hierarchy
- Approval state tracking
- Evidence metadata storage
- Role-based user mapping

---

## Technology Stack

### Backend
- Java
- Spring Boot
- Spring Data JPA
- Hibernate

### Workflow & Messaging
- Camunda 8
- Apache Kafka

### Security
- OAuth2
- OpenID Connect (OIDC)
- Keycloak

### Frontend
- Angular
- TypeScript

### Database
- MySQL

### Infrastructure
- Docker

---

## Engineering Focus

This project demonstrates:

- Modular backend architecture
- RESTful API design
- Workflow orchestration integration
- Event-driven communication
- Role-based access control
- Containerized deployment strategy

---

## Learning Outcomes

- Designing scalable backend systems
- Implementing workflow-based business processes
- Applying asynchronous messaging patterns
- Managing secure authentication flows
- Structuring maintainable service layers

---

## Future Improvements

- Horizontal scalability
- Observability (metrics & tracing)
- Cloud-native deployment
- Performance benchmarking

---

## Disclaimer

This repository documents the architectural design and implementation concepts of a Proof of Concept system developed in collaboration with an industry partner. Source code and business logic are not publicly shared due to confidentiality.
