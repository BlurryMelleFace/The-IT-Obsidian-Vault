---
tags:
  - devops
  - nodejs
  - javascript
  - npm
  - nvm
  - cheatsheet
---

# Node Tools (NVM & NPM)

> [!INFO]
> Essential commands for managing **Node.js** versions with **NVM** and project dependencies with **NPM**.

**Related Notes:**
- [[Docker]] – Dockerizing Node.js apps.
- [[IntelliJ]] – Great IDE for Node development.

---

## 🟢 NVM (Node Version Manager)

### Install & Manage Versions
1. **List Available (Remote)**:
   ```shell
   nvm ls-remote
   ```
2. **Install Version**:
   ```shell
   nvm install <version>
   ```
   *Example:* `nvm install 18` or `nvm install --lts`
3. **Use Version**:
   ```shell
   nvm use <version>
   ```
4. **Set Default Version**:
   ```shell
   nvm alias default <version>
   ```
5. **List Installed (Local)**:
   ```shell
   nvm ls
   ```
6. **Check Current Version**:
   ```shell
   nvm current
   ```

---

## 📦 NPM (Node Package Manager)

### Project Setup & Install
1. **Initialize Project**:
   ```shell
   npm init -y
   ```
2. **Install Dependencies** (from `package.json`):
   ```shell
   npm install
   ```
3. **Install Package**:
   ```shell
   npm install <package-name>
   ```
4. **Install Dev Dependency**:
   ```shell
   npm install -D <package-name>
   ```
5. **Install Global Package**:
   ```shell
   npm install -g <package-name>
   ```

### Update & Remove
6. **Update Packages**:
   ```shell
   npm update
   ```
7. **Uninstall Package**:
   ```shell
   npm uninstall <package-name>
   ```

### info & Scripts
8. **List Installed Packages**:
   ```shell
   npm list --depth=0
   ```
9. **View Outdated**:
   ```shell
   npm outdated
   ```
10. **Run Scripts**:
    ```shell
    npm run <script-name>
    ```
    *Common:* `npm start`, `npm test`, `npm run build`.
