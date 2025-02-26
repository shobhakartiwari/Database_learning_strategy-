# The 3 Layers of Databases

I was obsessed. I dove deep into 4 different databases—SQL and NoSQL—to understand:

- How they’re created  
- How they work internally  
- What they’re actually made of  

The deeper I went, the more complex it seemed. But then I saw the pattern.  

No matter how fancy or complex a database looks, they all boil down to **just 3 simple layers**. Yes, just 3.  

If you understand these layers, you can:  
- Grasp any database  
- Build deep intuition about its architecture  
- Answer any interview question confidently  

Here they are:

## 1. User Access Layer

This layer defines how users connect with the database.  

It includes:  
- **SQL** (Structured Query Language)  
- **HTTP APIs** (for NoSQL databases)  
- **Specific Protocols** (database-specific query languages)  

**Examples:**  
- RDBMS: SQL for user access  
- Cassandra: CQL (Cassandra Query Language)  
- NoSQL (DynamoDB, MongoDB): HTTP APIs  

---

## 2. Routing Layer

This layer routes read and write requests to the correct server or node.  

- Optional for single-node databases (e.g., traditional RDBMS)  
- Critical for distributed databases (NoSQL)  

**Examples:**  
- **DynamoDB**: Request router uses partition metadata to route reads/writes  
- **MongoDB**: Mongos connects to config servers for routing  
- **Cassandra**: Snitch finds the node where data resides  

**Pro Tip:** Almost all use **Consistent Hashing**—an efficient algorithm for distributing data across nodes for high availability and scalability.

---

## 3. Storage Layer

This layer defines how data is stored on disk. Two common data structures dominate:  

- **B/B+ Tree**:  
  - Used in 80% of databases (SQL and NoSQL)  
  - Offers consistent O(log n) read/write access  
  - Perfect for range queries  
  - Examples: All SQL DBs, DynamoDB, MongoDB  

- **LSM Tree**:  
  - Optimized for high write throughput  
  - Uses SSTable, compaction, and tombstones for efficient data management  
  - Examples: Cassandra, ScyllaDB  

---

## That’s It

All databases—SQL or NoSQL—are just a combination of these 3 layers.  

What surprised me most? Despite the marketing hype, SQL and NoSQL are fundamentally the same. They just assemble these layers differently.  

Next time you see a “new, fancy” database:  
- Don’t fall for buzzwords or social media hype  
- Apply this 3-layer framework  
- Break it down in 2 minutes flat  

This mindset shift will make you immune to hype and unmatched in system design interviews.
