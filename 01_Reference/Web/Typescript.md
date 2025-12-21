---
tags:
  - typescript
  - web
  - language
  - cheatsheet
  - javascript
---
# TypeScript

> [!INFO]
> **TypeScript** is a superset of JavaScript that adds static typing. It compiles down to plain JavaScript.

**Related Notes:**
- [[Angular]] – A framework using TypeScript.
- [[Node Tools]] – JS/TS tooling.

---

## 🏷️ Basic Types
```typescript
let isDone: boolean = false;
let decimal: number = 6;
let color: string = "blue";
let list: number[] = [1, 2, 3];
let tuple: [string, number] = ["hello", 10];
let random: any = 4; // Avoid when possible
let unknownType: unknown = 4; // Better than any
```

## 📐 Interfaces vs Types
### Interface (Extendable)
```typescript
interface User {
  id: number;
  name: string;
  count?: number; // Optional
}

interface Admin extends User {
  role: string;
}
```

### Type (Union/Intersection)
```typescript
type ID = string | number; // Union
type Coordinates = { x: number; y: number };
type AdminUser = User & { role: "admin" }; // Intersection
```

## 🧬 Generics
```typescript
function identity<T>(arg: T): T {
  return arg;
}

let output = identity<string>("myString");

interface Box<T> {
  contents: T;
}
```

## 🛠️ Utility Types
1. **Partial\<T\>** - Make all properties optional.
   ```typescript
   function update(user: User, fields: Partial<User>) { ... }
   ```
2. **Pick\<T, K\>** - Pick set of properties.
   ```typescript
   type UserPreview = Pick<User, "id" | "name">;
   ```
3. **Omit\<T, K\>** - Omit set of properties.
   ```typescript
   type UserPreview = Omit<User, "count">;
   ```
4. **Record\<K, T\>** - Dictionary with key K and value T.
   ```typescript
   const roles: Record<string, number> = { "admin": 1, "user": 2 };
   ```

## ⚙️ Configuration (tsconfig.json)
```json
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  }
}
```
