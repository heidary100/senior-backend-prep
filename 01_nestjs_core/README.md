# NestJS Core Mastery

This section covers the **deep internals of NestJS**, beyond basic usage. Understanding these concepts is essential for senior-level backend engineers.

---

## 1. Dependency Injection (DI)

### Key Concepts
- Providers are classes or values that NestJS can inject into other classes.
- **Scopes**:
  - `DEFAULT` (singleton per application)
  - `REQUEST` (one instance per request)
  - `TRANSIENT` (new instance every injection)
- NestJS uses **reflect-metadata** to handle decorators and DI.
- Modules declare providers and control visibility (`exports`).

### Common Pitfalls
- Circular dependencies (solve with `forwardRef`)
- Misusing scopes (e.g., injecting a request-scoped provider into singleton)

### Hands-On Example
```typescript
@Injectable({ scope: Scope.REQUEST })
export class RequestService {
  constructor(private readonly id: string) {}
}
