---
tags:
  - web
  - angular
  - frontend
  - typescript
  - cheatsheet
---

# Angular

> [!INFO]
> **Angular** is a platform for building mobile and desktop web applications.

**Related Notes:**
- [[Node Tools]] – Angular requires Node and NPM.
- [[CSS Tools]] – For styling.

---

## 🛠️ Installation & Setup
1. **Global CLI**:
   ```shell
   npm install -g @angular/cli
   ```
2. **New Project**:
   ```shell
   ng new my-angular-app
   cd my-angular-app
   ```
3. **Serve (Dev)**:
   ```shell
   ng serve
   ```

## 🏗️ Generators
- **Component**: `ng g c my-component`
- **Service**: `ng g s my-service`
- **Module**: `ng g m my-module`
- **Directive**: `ng g d my-directive`
- **Pipe**: `ng g p my-pipe`

## 📦 Build & Deploy
1. **Production Build**:
   ```shell
   ng build --configuration=production
   ```
2. **AOT Build**:
   ```shell
   ng build --aot
   ```

## 🧹 Maintenance (Clean Install)
> Use this if `node_modules` are broken.

1. **Delete**:
   ```powershell
   Remove-Item -Recurse -Force node_modules, package-lock.json
   ```
2. **Install Legacy Config** (if needed):
   ```shell
   npm install typescript@5.5.0 --save-dev --legacy-peer-deps
   npm install --legacy-peer-deps
   ```

## 🐞 Debugging Tips
1. **Inspect Component (Console)**:
   Select element in Elements tab, then:
   ```js
   ng.getComponent($0)
   ```
2. **Check Property**:
   ```js
   ng.getComponent($0).tableColumns
   ```
3. **Log Data in Component**:
   ```ts
   console.table(this.tableRows);
   ```