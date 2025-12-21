---
tags:
  - devops
  - redis
  - database
  - cache
  - cheatsheet
  - cli
---
# Redis (Remote Dictionary Server)

> [!INFO]
> **Redis** is an open-source, in-memory data structure store, used as a database, cache, and message broker. It supports various data structures such as strings, hashes, lists, sets, and sorted sets.

**Related Notes:**
- [[Docker]] – Often used to run Redis containers.
- [[AWS]] – For ElastiCache (managed Redis).

---

## 🔌 Connection
1. **Connect to Local Server**:
   ```shell
   redis-cli
   ```
2. **Connect to Remote Host**:
   ```shell
   redis-cli -h <hostname> -p <port> -a <password>
   ```
3. **Ping Server**:
   ```shell
   redis-cli ping
   # Output: PONG
   ```

## 🗝️ Keys (Basic Operations)
1. **Set Key**:
   ```shell
   SET mykey "Hello World"
   ```
2. **Get Key**:
   ```shell
   GET mykey
   ```
3. **Delete Key**:
   ```shell
   DEL mykey
   ```
4. ** Check if Key Exists**:
   ```shell
   EXISTS mykey
   # Returns 1 if exists, 0 otherwise
   ```
5. **Set Expiration (TTL)**:
   ```shell
   EXPIRE mykey 60
   # Expires in 60 seconds
   ```
6. **Find Keys (Pattern)**:
   ```shell
   KEYS *
   KEYS user:*
   ```

## 📝 Lists
1. **Push to Left (Head)**:
   ```shell
   LPUSH mylist "value"
   ```
2. **Push to Right (Tail)**:
   ```shell
   RPUSH mylist "value"
   ```
3. **Pop from Left**:
   ```shell
   LPOP mylist
   ```
4. **Get Range (All)**:
   ```shell
   LRANGE mylist 0 -1
   ```

## #️⃣ Hashes
1. **Set Hash Field**:
   ```shell
   HSET myhash field1 "Hello"
   ```
2. **Get Hash Field**:
   ```shell
   HGET myhash field1
   ```
3. **Get All Fields & Values**:
   ```shell
   HGETALL myhash
   ```
4. **Delete Field**:
   ```shell
   HDEL myhash field1
   ```

## 🧊 Sets
1. **Add Member**:
   ```shell
   SADD myset "member1"
   ```
2. **Get All Members**:
   ```shell
   SMEMBERS myset
   ```
3. **Check Membership**:
   ```shell
   SISMEMBER myset "member1"
   ```
4. **Remove Member**:
   ```shell
   SREM myset "member1"
   ```

## 🛠️ Troubleshooting
1. **Monitor All Commands**:
   ```shell
   redis-cli monitor
   ```
   > [!WARNING]
   > Creates high load. Use with caution in production.

2. **Server Info & Stats**:
   ```shell
   redis-cli info
   ```
3. **Slow Log**:
   ```shell
   redis-cli slowlog get 10
   ```
