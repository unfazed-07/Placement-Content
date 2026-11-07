# Ranked Core CS Face-to-Face Interview Questions (< 10 LPA)

**Target Roles:** TCS (Ninja/Digital/Prime), Infosys (SE/DSE/SP), Cognizant (GenC/GenC Next), Accenture, Capgemini, Deloitte, Wipro, LTIMindtree, ZS Associates, and mid-tier product companies (4–10 LPA).

In face-to-face technical rounds under 10 LPA, core subjects are not tested equally. Based on thousands of campus interview experiences, here is the exact **Subject Weightage Breakdown** in a 30-to-45-minute technical interview:

1. **Object-Oriented Programming (OOPs): ~40% of Core Questions** *(Asked in 9 out of 10 interviews)*
2. **DBMS & SQL: ~35% of Core Questions** *(Asked in 8.5 out of 10 interviews)*
3. **Operating Systems (OS): ~15% of Core Questions** *(Asked in 5 out of 10 interviews, higher in 7–10 LPA roles)*
4. **Computer Networks & Web (CN): ~10% of Core Questions** *(Usually 1–2 questions linked to your web/cloud project)*

---

## Part 1: The Overall Top 12 Most Frequent Face-to-Face Questions (Ranked Highest to Lowest)

*If you only have 3 hours before an interview, master these 12 questions in this exact order. Together, they account for **85%+ of all Core CS questions** asked in sub-10 LPA interviews.*

### Rank #1: Explain the 4 Pillars of OOPs with a real-life or project example.
* **Subject:** OOPs | **Probability of Being Asked:** **~88%**
* **Why it's #1:** Almost every technical interviewer uses this as their opening warm-up question after "Tell me about yourself."
* **What the interviewer listens for:**
  * **Encapsulation:** Binding data and methods together and hiding internal state using `private` variables and `public` getters/setters.
  * **Abstraction:** Hiding complex implementation details and only showing essential features to the user (via Interfaces/Abstract classes).
  * **Inheritance:** Acquiring properties of a parent class (`IS-A` relationship) for code reusability.
  * **Polymorphism:** Same interface/method name behaving differently based on the object or parameters.
* **Trap to avoid:** Do not give the textbook "Animal $\rightarrow$ Dog" or "Car $\rightarrow$ Engine" example. Use a module from your resume project (e.g., `PaymentGateway` interface implemented by `UPIPayment` and `CardPayment`).

### Rank #2: Compile-Time vs. Runtime Polymorphism (Method Overloading vs. Overriding)
* **Subject:** OOPs | **Probability of Being Asked:** **~80%**
* **What the interviewer listens for:**
  * **Overloading (Compile-Time / Static Binding):** Same method name, different parameter count or types, happens within the *same* class.
  * **Overriding (Runtime / Dynamic Binding):** Same method name and exact same parameter signature in a *child* class. Resolved at runtime using Virtual Method Tables (`vtable` in C++) or Dynamic Method Dispatch (Java).
* **Immediate Follow-up (~65% chance):** *"Can we override a `static`, `private`, or `final` method?"* (Answer: **No**. Static methods belong to the class, not the object; private methods are invisible to child classes; final methods explicitly forbid overriding).

### Rank #3: SQL Joins (INNER, LEFT, RIGHT, FULL, SELF) + The "2nd Highest Salary" Query
* **Subject:** DBMS / SQL | **Probability of Being Asked:** **~78%**
* **What the interviewer listens for:** They will almost always draw two small tables (`Table A` with IDs `1, 1, 2, NULL` and `Table B` with IDs `1, 2, 3, NULL`) and ask how many rows `INNER JOIN` and `LEFT JOIN` will return.
* **Must-Know Live Query:**
  ```sql
  -- Nth Highest Salary (Using DENSE_RANK handles duplicate salaries properly)
  SELECT salary FROM (
      SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) as rnk 
      FROM Employees
  ) t WHERE rnk = 2;
  ```

### Rank #4: Primary Key vs. Unique Key vs. Foreign Key
* **Subject:** DBMS | **Probability of Being Asked:** **~72%**
* **What the interviewer listens for:**
  * **Primary Key:** Uniquely identifies a record. Cannot be `NULL`. Only **one** per table. Automatically creates a **Clustered Index**.
  * **Unique Key:** Uniquely identifies a record, but allows **one `NULL` value** (in most RDBMS). A table can have **multiple** Unique Keys. Creates a **Non-Clustered Index**.
  * **Foreign Key:** A column referencing the Primary Key of another table to enforce referential integrity. Can have duplicates and `NULL` values.

### Rank #5: Abstract Class vs. Interface — What is the difference and when to use which?
* **Subject:** OOPs | **Probability of Being Asked:** **~68%**
* **What the interviewer listens for:**
  * **Abstract Class:** Can have both abstract and concrete methods, instance variables, and **constructors**. Supports single inheritance. Use when classes share a strict identity (`IS-A`).
  * **Interface:** Blueprint of behavior (100% abstract prior to Java 8; `default` and `static` methods allowed since Java 8). Variables are `public static final` by default. **No constructors**. Supports **Multiple Inheritance**.
* **Immediate Follow-up:** *"What is the Diamond Problem and how do Interfaces solve it?"*

### Rank #6: ACID Properties in DBMS (with a Bank/UPI Transfer Example)
* **Subject:** DBMS | **Probability of Being Asked:** **~62%**
* **What the interviewer listens for:**
  * **Atomicity:** "All or Nothing." If ₹500 is debited from Account A and the server crashes before crediting Account B, the transaction rolls back completely.
  * **Consistency:** Database constraints (like total balance across accounts) remain valid before and after the transaction.
  * **Isolation:** Two people sending money to the same account simultaneously do not overwrite each other's intermediate balance.
  * **Durability:** Once a transaction is committed, changes persist in non-volatile storage even if power fails immediately after.

### Rank #7: `DELETE` vs. `TRUNCATE` vs. `DROP` (and `WHERE` vs. `HAVING`)
* **Subject:** DBMS / SQL | **Probability of Being Asked:** **~58%**
* **What the interviewer listens for:**
  * `DELETE` (DML): Removes specific rows using `WHERE`. Logs every row deletion, slower, **can be rolled back**.
  * `TRUNCATE` (DDL): Removes all rows at once by deallocating data pages. Preserves table structure. Much faster, **cannot be rolled back** in standard usage.
  * `DROP` (DDL): Deletes all rows **plus the table schema/structure itself** from the database.
  * `WHERE` filters individual rows *before* grouping (`GROUP BY`); `HAVING` filters aggregated groups *after* `GROUP BY`.

### Rank #8: Database Normalization (1NF, 2NF, 3NF, BCNF)
* **Subject:** DBMS | **Probability of Being Asked:** **~52%**
* **What the interviewer listens for:** Normalization reduces data redundancy and prevents **Insertion, Update, and Deletion anomalies**.
  * **1NF:** Every cell holds a single atomic value (no comma-separated values).
  * **2NF:** In 1NF + **No Partial Dependency** (non-prime attributes must depend on the *entire* composite primary key, not just part of it).
  * **3NF:** In 2NF + **No Transitive Dependency** (non-prime attribute cannot depend on another non-prime attribute).
  * **BCNF:** Strict 3NF where for every functional dependency $X \rightarrow Y$, $X$ must be a Super Key.

### Rank #9: Process vs. Thread (and Stack vs. Heap Memory)
* **Subject:** Operating Systems / Language Internals | **Probability of Being Asked:** **~48%**
* **What the interviewer listens for:**
  * **Process:** An executing program with its own isolated memory space (Heavyweight, slow context switching, uses IPC to communicate).
  * **Thread:** Lightweight execution unit inside a process. Threads of the same process **share the Code, Data, and Heap segments**, but each has its **own Stack and Registers**.
  * **Stack vs. Heap:** Stack stores local primitive variables and method call frames (LIFO, fast, automatic cleanup); Heap stores objects dynamically created at runtime (`new`), cleaned up by Garbage Collection.

### Rank #10: Deadlock — 4 Necessary Conditions & How to Prevent It
* **Subject:** Operating Systems | **Probability of Being Asked:** **~42%**
* **What the interviewer listens for:** A situation where two or more processes wait indefinitely for resources held by each other.
  * **4 Coffman Conditions:** Mutual Exclusion, Hold and Wait, No Preemption, Circular Wait.
  * **Prevention:** Eliminate any one condition—most commonly **Circular Wait** by enforcing a strict increasing order of resource acquisition.

### Rank #11: Database Indexing — How it works and why we don't index every column
* **Subject:** DBMS | **Probability of Being Asked:** **~38%** *(Very high ~70% in 7–10 LPA roles like TCS Prime, Infosys SP, Deloitte)*
* **What the interviewer listens for:**
  * Indexes use **B-Trees or B+ Trees** to store pointers to rows in sorted order, dropping query search complexity from $O(n)$ full-table scan to $O(\log n)$.
  * **Downside:** Indexes consume disk space and **slow down `INSERT`, `UPDATE`, and `DELETE` queries** because the B+ Tree must be updated and rebalanced on every write.

### Rank #12: What happens behind the scenes when you type `google.com` in a browser? (Plus TCP vs. UDP & HTTP Methods)
* **Subject:** Computer Networks | **Probability of Being Asked:** **~35%**
* **What the interviewer listens for:**
  1. **DNS Resolution:** Translates `google.com` to an IP address.
  2. **TCP 3-Way Handshake:** `SYN` $\rightarrow$ `SYN-ACK` $\rightarrow$ `ACK` establishes connection.
  3. **SSL/TLS Handshake:** Establishes HTTPS encryption.
  4. **HTTP Request/Response:** Browser sends `GET` request; server responds with status code (`200 OK`, `404 Not Found`, `500 Internal Server Error`) and HTML.
* **Follow-up:** **TCP** is connection-oriented and reliable (used in web browsing, emails, file transfers); **UDP** is connectionless and fast with no retransmission (used in live video streaming, VoIP, DNS, online gaming).

---

## Part 2: Subject-by-Subject Rapid-Fire Breakdown (With Exact Frequency)

If an interviewer decides to drill deeper into a specific subject based on your resume, here are the exact secondary questions ranked by frequency within each subject:

### 1. OOPs & Programming Language Internals (Weightage: 40%)
| Rank in Subject | Question | Interview Probability |
| :--- | :--- | :--- |
| **1** | 4 Pillars of OOPs with real-world/project code example | **88%** |
| **2** | Method Overloading vs. Method Overriding | **80%** |
| **3** | Abstract Class vs. Interface | **68%** |
| **4** | Constructors (Default, Parameterized, Copy) & Can a constructor be `private`? *(Yes, used in Singleton Pattern)* | **55%** |
| **5** | Access Modifiers (`public`, `private`, `protected`, `default`) | **50%** |
| **6** | Language-Specific Classic: **`==` vs `.equals()` & why Strings are Immutable** (Java) OR **Pointers vs. References & Virtual Functions** (C++) | **48%** |
| **7** | Exception Handling (`try`, `catch`, `finally`, `throw` vs `throws`) & Does `finally` always execute? | **42%** |
| **8** | Memory Management: Garbage Collection (Java) / `malloc` vs `new` & Destructors (C++) | **35%** |

### 2. DBMS & SQL (Weightage: 35%)
| Rank in Subject | Question | Interview Probability |
| :--- | :--- | :--- |
| **1** | Types of SQL Joins + Predicting row output on sample tables | **78%** |
| **2** | Write a query for 2nd / $N$-th Highest Salary or Department-wise Highest Salary | **75%** |
| **3** | Primary Key vs. Unique Key vs. Foreign Key vs. Candidate Key | **72%** |
| **4** | ACID Properties with transaction example | **62%** |
| **5** | `DELETE` vs. `TRUNCATE` vs. `DROP` & `WHERE` vs. `HAVING` | **58%** |
| **6** | Normalization (1NF, 2NF, 3NF, BCNF) | **52%** |
| **7** | Indexing (Clustered vs. Non-Clustered Index) | **38%** |
| **8** | SQL vs. NoSQL (Relational vs. Non-Relational—especially if MongoDB is on your resume) | **34%** |

### 3. Operating Systems (Weightage: 15%)
| Rank in Subject | Question | Interview Probability |
| :--- | :--- | :--- |
| **1** | Process vs. Thread | **48%** |
| **2** | Deadlock (4 Conditions & Prevention/Avoidance) | **42%** |
| **3** | Virtual Memory, Paging, Page Faults, and Thrashing | **35%** |
| **4** | CPU Scheduling Algorithms (FCFS, SJF, Round Robin, Starvation & Aging) | **30%** |
| **5** | Mutex vs. Semaphore & Race Condition / Critical Section | **26%** |
| **6** | Fragmentation (Internal vs. External) & Paging vs. Segmentation | **18%** |

### 4. Computer Networks & Web Fundamentals (Weightage: 10%)
| Rank in Subject | Question | Interview Probability |
| :--- | :--- | :--- |
| **1** | TCP vs. UDP (with real-world use cases) | **40%** |
| **2** | HTTP vs. HTTPS & HTTP Methods (`GET` vs. `POST` vs. `PUT` vs. `DELETE`) | **38%** |
| **3** | What happens when you enter a URL in the browser? (DNS + TCP Handshake) | **35%** |
| **4** | OSI Model (7 Layers) vs. TCP/IP Model — Name the layers and protocols at each layer | **28%** |
| **5** | IPv4 vs. IPv6 & Public vs. Private IP / MAC Address vs. IP Address | **20%** |
| **6** | Common HTTP Status Codes (`200`, `201`, `400`, `401` vs `403`, `404`, `500`) | **18%** |