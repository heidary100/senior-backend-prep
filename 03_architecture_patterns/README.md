# Architecture Patterns for Senior Backend Engineers

Understanding **architecture patterns** is essential for building scalable and maintainable systems.

---

## 1. Monolith vs Microservices

### Monolith
- Single deployable
- Easier to debug
- Can scale vertically

### Microservices
- Independently deployable services
- Scale horizontally
- Need event-driven or API communication
- More operational complexity

### Hands-On Example
- Convert a **NestJS monolith** CRUD app into **2 services**:
  - `users-service`
  - `orders-service`
- Communicate via **RabbitMQ or Kafka**.

---

## 2. Domain-Driven Design (DDD)

- **Entities, Value Objects, Aggregates**
- **Repositories** abstract data layer
- Use **Bounded Contexts** to separate domains

### Hands-On Example
- Build a **User & Payment bounded context**:
  - Entities: `User`, `Payment`
  - Repositories: `UserRepository`, `PaymentRepository`
  - Aggregate root for `Payment`

---

## 3. CQRS (Command Query Responsibility Segregation)

- **Separate read & write models**
- Useful for high-load systems
- Can integrate with event sourcing

### Hands-On Example
- Build a **NestJS app**:
  - Commands: `CreateUserCommand`
  - Queries: `GetUserQuery`
- Show how **event bus** propagates changes

---

## 4. Event-Driven Architecture

- Services communicate via **events** instead of direct calls
- Enables **loose coupling** and async processing
- Can use RabbitMQ, Kafka, or Redis streams

### Hands-On Example
- Build a **NestJS microservice**:
  - User service emits `UserCreated` event
  - Notification service listens and sends email
- Include **retry and error handling logic**

---

## Recommended Exercises
1. Draw a **module diagram** of a real microservice system.
2. Implement **DDD aggregates and repositories** in NestJS.
3. Build a **CQRS + event-driven example** using NestJS + BullMQ.
