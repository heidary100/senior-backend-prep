
---

# 02_typescript_mastery/README.md

```markdown
# TypeScript Mastery for Senior Backend Engineers

Understanding TypeScript deeply is crucial for NestJS projects at scale.

---

## 1. Advanced Types

- **Union & Intersection Types**
- **Mapped Types**
- **Conditional Types**
- **Discriminated Unions**
- **Template Literal Types**

### Hands-On Example
```typescript
type ApiResponse<T> = { success: true; data: T } | { success: false; error: string };
