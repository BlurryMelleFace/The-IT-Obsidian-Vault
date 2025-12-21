---
tags:
  - aws
  - devops
  - database
  - nosql
  - cheatsheet
---
# DynamoDB

> [!INFO]
> **DynamoDB** is a fully managed NoSQL database service provided by AWS. It provides fast and predictable performance with seamless scalability.

**Related Notes:**
- [[AWS]] – Managing DynamoDB via CLI.
- [[Database/PostgresSQL]] – Contrast with Relational DB.

---

## 🔑 Key Concepts
- **Table**: Collection of data.
- **Item**: A single record (like a row).
- **Attribute**: A data element (like a column).
- **Primary Key**:
    - **Partition Key** (PK): Determines distribution.
    - **Sort Key** (SK): Ensorbits items within a partition.

## 🛠️ CLI Commands
1. **List Tables**:
   ```shell
   aws dynamodb list-tables
   ```
2. **Scan Table** (Read All - **Expensive!**):
   ```shell
   aws dynamodb scan --table-name MyTable
   ```
3. **Get Item**:
   ```shell
   aws dynamodb get-item --table-name MyTable --key '{"PK": {"S": "some-id"}}'
   ```
4. **Put Item**:
   ```shell
   aws dynamodb put-item --table-name MyTable --item '{"PK": {"S": "123"}, "Name": {"S": "Alice"}}'
   ```
5. **Query** (By PK):
   ```shell
   aws dynamodb query --table-name MyTable --key-condition-expression "PK = :pk" --expression-attribute-values '{":pk": {"S": "123"}}'
   ```

## ⚖️ Capacity Modes
- **On-Demand**: Pay per request. Good for unpredictable workloads.
- **Provisioned**: Specify Read/Write Capacity Units (RCU/WCU). Cheaper for steady traffic.
