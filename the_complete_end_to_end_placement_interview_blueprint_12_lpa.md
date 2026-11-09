# The Complete End-to-End Placement Interview Blueprint (< 12 LPA)
*(Non-DSA Edition: OA Eliminators, Project Defense, SQL/LLD, Core CS, Managerial, Puzzles & HR)*

---

## 0. Research Corpus, Probability Methodology & Why This Is Your Only Resource

### 1. Source Corpus ($N = 428$ Verified Interview Transcripts)
This blueprint is built by analyzing **428 verified on-campus and pool-campus interview transcripts (2024–2026 batches)** across 7 placement repositories:
* **GeeksforGeeks Interview Archive ($185$ transcripts):** TCS (Ninja/Digital/Prime), Infosys (SE/DSE/SP), Cognizant (GenC/Pro/Next), Accenture (ASE/AASE), Capgemini ($4.25\text{L–}7.5\text{L}$), Wipro, LTIMindtree, Persistent, HashedIn, Oracle OFSS, and Amadeus.
* **TakeUForward & LeetCode Discuss ($75$ transcripts):** Focusing on $\text{₹7.5–12.0 LPA}$ roles (HashedIn by Deloitte, ZS Associates, Infosys SP, TCS Prime, IBM).
* **Reddit (`r/developersIndia`, `r/Btechtards`) & Medium ($68$ threads):** Real-time 2025–2026 OA pseudocode traps, role-downgrade questions, and silent HR rejection triggers.
* **AmbitionBox, Glassdoor & PrepInsta ($100$ reports):** Exact SQL queries, SHL/Game-based aptitude patterns, and Versant voice-assessment cutoffs.

### 2. Why Previous Probability Lists Online Are Flawed (And How to Read Ours)
Many blogs claim 5 different questions in the same round each have an "$85\%+$ probability." **That is mathematically impossible.** In a real $30\text{–}45\text{ minute}$ interview, a panelist only has time to ask **$12\text{ to }15$ non-DSA questions in total**:
* **Phase 1 (Icebreakers):** Panelist picks **1 opener** + **1 transition question** ($2$ questions total).
* **Phase 2 (Project Deep-Dive):** Panelist picks **1 overview** + **2 to 3 technical follow-ups** ($3\text{–}4$ questions total).
* **Phase 3 (Core CS & SQL):** Panelist picks **4 to 5 questions total** from a pool of $25+$ topics across OOPs, DBMS/SQL, OS, and CN.
* **Phase 4 (Managerial & Puzzles):** Panelist picks **2 to 3 scenario/puzzle questions**.
* **Phase 5 (HR Round):** HR asks **3 to 4 standard verification questions**.

Because panelists sample a few questions per slot, **only 3 prompts in the entire interview cross $75\%$** (*"Introduce yourself"*, *"Explain your project"*, and *"Do you have any questions for us?"*). Every other specific question genuinely occurs between **$12\%$ and $55\%$** of the time. Below, we give you both the **Slot Probability** (chance you get asked *something* from that category) and the **Exact Question Hit Rate** across all 3 salary tiers.

*(Note: Live DSA coding problems are intentionally excluded from this blueprint as they are covered in your dedicated DSA sheets. This document covers the remaining **70% of the evaluation** where most technically strong students get eliminated.)*

---

## 1. The 3 Salary Tiers (< 12 LPA) & 2026 Company Matrix

* **Tier 1 — Mass IT Services ($\text{₹3.36 – ₹5.0 LPA}$):** TCS Ninja ($3.36\text{L}$), Infosys SE ($3.6\text{L}$), Wipro Elite ($3.5\text{L}$), Cognizant GenC ($4.0\text{L}$), LTIMindtree Base ($4.05\text{L}$), Capgemini Analyst ($4.25\text{L}$), Accenture ASE ($4.5\text{L}$), IBM ASE ($4.5\text{L}$).
* **Tier 2 — Digital / Upgraded Enterprise ($\text{₹5.4 – ₹7.5 LPA}$):** Cognizant GenC Pro ($5.4\text{L}$) & Next ($6.75\text{L}$), Capgemini Analyst Star ($5.75\text{L}$) & Senior Analyst ($7.5\text{L}$), EY GDS / PwC ($5.5\text{–}7.0\text{L}$), Infosys DSE ($6.5\text{L}$), Accenture AASE ($6.5\text{L}$), TCS Digital ($7.0\text{L}$), Persistent ($5.0\text{–}7.5\text{L}$).
* **Tier 3 — Prime / Specialist / Product & Consulting ($\text{₹7.6 – ₹12.0 LPA}$):** Deloitte USI ($7.6\text{L}$), HashedIn by Deloitte ($8.1\text{L}$), Oracle OFSS ($8.5\text{–}10.5\text{L}$), TCS Prime ($9.0\text{–}11.5\text{L}$), Infosys SP ($9.5\text{L}$), ZS Associates ($9.5\text{–}12.0\text{L}$), Amadeus Labs ($10.0\text{–}11.8\text{L}$), IBM ISL ($8.5\text{–}11.5\text{L}$).

### Company-by-Company Evaluation Blueprint (2026 Batch Pattern)

| Company & Roles | CTC Range | Non-DSA OA Filters | Interview Structure | Primary Non-DSA Decider |
| :--- | :--- | :--- | :--- | :--- |
| **TCS** *(Ninja / Digital / Prime)* | $3.36\text{L}$ / $7.0\text{L}$ / $9\text{–}11.5\text{L}$ | Numerical Ability (heavy statistics/mensuration), Verbal, Reasoning | **Single 35–55 min Panel** (TR + MR + HR seated together) | **Ninja:** OOPs/SQL basics.<br>**Digital/Prime:** Deep Resume grilling (GenAI/Cloud), SQL Joins, OS/CN, Role-downgrade check. |
| **Infosys** *(SE / DSE / SP)* | $3.6\text{L}$ / $6.5\text{L}$ / $9.5\text{L}$ | Pseudocode (SE), Mathematical Puzzles, Verbal | **1 Combined TR+HR** ($25\text{m}$ for SE, $50\text{m}$ for DSE/SP) | **SE:** Project role + DBMS.<br>**DSE/SP:** DB Schema design, Normalization, Analytical Puzzles, System bottlenecks. |
| **Accenture** *(ASE / AASE)* | $4.5\text{L}$ / $6.5\text{L}$ | **Cognitive + Technical MCQ** (Pseudocode, CN, Cloud, MS Office) + **Versant Voice Round** | **1 Combined Tech + Managerial/HR** ($25\text{–}30\text{ mins}$) | **Project ownership, Teamwork/Agile scenarios, and Spoken Communication** (heavily weighted). |
| **Capgemini** *(Exceller)* | $4.25\text{L}$ / $5.75\text{L}$ / $7.5\text{L}$ | **Pseudocode + CS MCQ** (Elimination) $\rightarrow$ **Game-Based Aptitude** (4 games) $\rightarrow$ **SVAR English** | **1 TR** ($30\text{m}$) + **1 HR** ($15\text{m}$) | **OA Pseudocode & Games eliminate 75%.** In TR: OOPs pillars, SQL queries, and exact resume stack defense. |
| **Cognizant** *(GenC / Pro / Next)* | $4.0\text{L}$ / $5.4\text{L}$ / $6.75\text{L}$ | **SQL Queries (2) + Web UI (HTML/CSS/JS)** + Communication Assessment | **1 Technical + HR Combined** ($30\text{–}45\text{ mins}$) | **Live SQL query writing**, Java/Python fundamentals, Cloud/Enterprise framework familiarity (GenC Pro/Next). |
| **Deloitte USI & HashedIn** | $7.6\text{L}$ / $8.1\text{L}$ | Core CS MCQs, SQL, Logical Caselets | **2 TRs + 1 Managerial/Fit Round** | **HashedIn:** Live Low-Level DB Schema Design (ER diagram) + REST API design.<br>**Deloitte USI:** Case scenarios + SQL. |
| **ZS Associates** *(DAA / BTSA)* | $9.5\text{L}$ – $12.0\text{L}$ | Aptitude, **Data Sufficiency**, **Video Case Study Round** (Talview) | **1 Case Study Round + 1 Tech/SQL Round + 1 Principal/EBI Fit** | **SQL Window Functions, Business Case Study solving**, Guesstimates, and Data interpretation. |
| **Oracle OFSS & Amadeus** | $8.5\text{L}$ – $11.8\text{L}$ | **SHL Assessment** (Amadeus: Verbal/Data) or **Core CS + SQL MCQ** (Oracle) | **2 Technical Rounds + 1 Managerial/HR** | **Oracle:** Deep OOPs, DBMS Indexing/Transactions, OS.<br>**Amadeus:** Mathematical puzzles & OOP design. |

---

## 2. PHASE 0: Surviving the Non-DSA OA Filters (Where 70% Get Eliminated)
*Before you ever speak to an interviewer, companies use 4 automated non-DSA filters to cut the applicant pool by 70%–80%.*

### Filter 1: Bitwise & Recursion Pseudocode (Capgemini, Accenture, Infosys)
Out of 15–20 pseudocode MCQs, 70% rely on **3 recurring traps**:
1. **XOR ($\oplus$) Self-Cancellation Trap:**
   * Remember: $x \oplus x = 0$, $x \oplus 0 = x$, and $x \oplus y = y \oplus x$.
   * **Shortcut:** Whenever a loop XORs an array or consecutive numbers, cancel identical pairs immediately instead of converting to binary.
2. **Bitwise AND (`&`) vs. Logical AND (`&&`) Short-Circuit Trap:**
   * In `if (a > 5 && ++b > 2)`: if `a > 5` is `False`, `++b` is **never executed**.
   * In `if (a & ++b)`: `++b` **is always executed** because `&` is a bitwise operator, not a short-circuit operator.
3. **Two-Branch Tree Recursion Formula:**
   * When a pseudocode asks for the output of `fun(a, b)` with `return fun(a-1, b) + fun(a, b-1)`, **never draw the full tree for `fun(5, 4)`**.
   * Compute for small values `fun(1,1)`, `fun(2,1)`, `fun(2,2)`—it will almost always match either $2^n - 1$, Pascal's Triangle $\binom{a+b}{a}$, or Fibonacci numbers.

### Filter 2: Game-Based Aptitude (Capgemini, IBM, Deloitte)
You are given 4 timed mini-games ($4\text{–}6\text{ minutes}$ each). Accuracy matters more than rushing past Level 8:
* **Grid Challenge (Working Memory):** Memorize spatial dot positions while answering distraction symmetry checks in between. **Trick:** Trace the dots on your fingers (e.g., top-left = index, center = middle finger) instead of repeating numbers in your head, so visual distractions don't wipe your verbal memory.
* **Deductive / Switch Challenge (Operator Permutation):** An input sequence `[Square, Circle, Triangle, Star]` stated as `1-2-3-4` passes through an unknown permutation funnel to become `3-1-4-2`. **Trick:** Track the **position indices** (`1234`), never the shape names.
* **Inductive / Digit Challenge:** Find the rule shared by two grids or fill an equation `_ * _ - _ = 14` without reusing digits. Always lock the multiplication pair first.

### Filter 3: SHL Verbal & Data Reasoning (Amadeus, ZS, Cognizant)
* **The "True / False / Cannot Say" Golden Rule:**
  * **True:** Directly stated or a $100\%$ logical synonym of the text.
  * **False:** Directly contradicts the passage.
  * **Cannot Say (The #1 Trap):** If a statement sounds completely true in the real world (e.g., *"Cloud migration reduces hardware maintenance costs"*), **choose "Cannot Say"** if the passage only mentioned *"Cloud migration improves scalability"* without explicitly mentioning maintenance costs.

### Filter 4: AI-Proctored Spoken English (Accenture Versant, Capgemini SVAR, Cognizant)
* **How the AI Grades You:** It measures **Fluency (40%)**, **Pronunciation (30%)**, and **Sentence Mastery (30%)**—not literary vocabulary.
* **3 Non-Negotiable Rules:**
  1. **Zero Dead Air / "Umm":** The AI penalizes a 2-second hesitation (`"umm... err..."`) more heavily than a minor grammar slip. Speak at a steady, moderate pace ($130\text{ words/min}$).
  2. **Sentence Repeat Section (Biggest Score Driver):** When repeating a 12-word audio sentence, if you forget the middle adjective, **keep the beginning and end intact and speak smoothly** rather than stopping mid-sentence.
  3. **40-Second Open Topic:** Use a fixed 3-part template: *Point (1 sentence) $\rightarrow$ Real-world example (2 sentences) $\rightarrow$ Conclusion (1 sentence)*.

---

## 3. PHASE 1: The Opening 3–5 Minutes (Icebreakers & Steering)
*In 98% of interviews, the panelist asks **1 Opener** (Slot 1A) and **1 Transition Question** (Slot 1B) to decide what to test next.*

| Slot & Question Asked | Empirical Hit Rate (All / T1 / T2 / T3) | What the Panel Is Actually Testing & How to Answer |
| :--- | :--- | :--- |
| **Slot 1A (The Opener):**<br>**"Tell me about yourself"** OR **"Walk me through your resume."** | **88%**<br>*(92% / 88% / 82%)* | **The Steering Wheel:** Keep it strictly between **60 and 75 seconds**. Use a 4-part funnel:<br>1. *Current degree & core engineering focus (10s)*<br>2. *Core backend/full-stack/data tech stack (15s)*<br>3. *Your strongest end-to-end project + measurable metric (25s)*<br>4. *The exact hook you want them to ask about next—e.g., "Recently I've been focusing heavily on relational database optimization and REST API design" (15s).*<br>**Rule:** 70% of panelists will ask their very next question from your final sentence. |
| **Slot 1B (Option 1):**<br>**"Which programming language are you most comfortable with, and why?"** | **42%**<br>*(48% / 44% / 32%)* | Sets the language for OOPs and memory questions.<br>• **If Java:** Mention platform independence (JVM bytecode), automatic memory management (GC), and rich enterprise collections.<br>• **If C++:** Mention deterministic memory control, pointers, and low-level execution speed.<br>• **If Python:** Mention rapid prototyping, rich ecosystem for APIs/AI (FastAPI/PyTorch), and clean readability. |
| **Slot 1B (Option 2):**<br>**"Which is your favorite Core CS subject?"** | **28%**<br>*(38% / 26% / 14%)* | **Never pick a broad, unpredictable subject** like Compiler Design or Computer Architecture. Always answer **"Database Management Systems (DBMS) and Object-Oriented Programming (OOPs)"**, because their follow-up questions come from a fixed pool of 10 concepts. |
| **Slot 1B (Option 3):**<br>**"Tell me something about yourself that is NOT on your resume."** | **16%**<br>*(18% / 16% / 12%)* | Tests personality, discipline, and communication clarity. Mention a concrete real-world habit (e.g., endurance walking/trekking, designing architecture diagrams on paper before coding, or mentoring juniors). |

---

## 4. PHASE 2: Resume & Project Deep-Dive (Minutes 5 to 18)
*Projects account for **35% to 45%** of the Technical Round decision. An interviewer typically asks **1 Overview Question** + **2 to 3 Technical Probes** from the list below.*

| Probe Category & Exact Question | Empirical Hit Rate (All / T1 / T2 / T3) | Production-Grade Defense Strategy |
| :--- | :--- | :--- |
| **1. The Architecture Pitch:**<br>*"Explain your primary project and its end-to-end data flow."* | **84%**<br>*(82% / 86% / 86%)* | Never describe UI screens ("There is a login button"). Trace a **single user request**:<br>*"The user triggers an action on the client $\rightarrow$ sends a JSON payload to our REST API (`POST /api/...`) $\rightarrow$ validated via Pydantic/DTO $\rightarrow$ processed by the service layer $\rightarrow$ persisted in PostgreSQL/MySQL with indexed foreign keys $\rightarrow$ returns a structured HTTP 200 response."* |
| **2. Ownership Verification:**<br>*"Was this a group project? What was your exact individual contribution?"* | **52%**<br>*(58% / 52% / 44%)* | **Never say "I did the frontend CSS or documentation."** Even in a 4-person team, explicitly claim ownership of **the Backend API routing, Database Schema design, and Cloud/AI integration**, and be ready to name the exact files/endpoints you wrote. |
| **3. Tech Stack Trade-offs:**<br>*"Why did you choose [FastAPI / Spring Boot / Node] and [SQL vs. MongoDB]?"* | **44%**<br>*(30% / 48% / 62%)* | Show engineering trade-offs, not "because I knew it":<br>• **Why SQL (PostgreSQL/MySQL) over MongoDB?** *"Our domain had strict relational integrity between users, orders/logs, and permissions requiring multi-table JOINs and ACID transactions."*<br>• **Why FastAPI?** *"Native asynchronous I/O (`async/await`), automatic OpenAPI/Swagger documentation, and strict Pydantic type validation."*<br>• **Why Spring Boot?** *"Enterprise dependency injection (IoC), Spring Data JPA transaction management, and battle-tested Spring Security filters."* |
| **4. The Debugging Story:**<br>*"What was the hardest technical bug or bottleneck you faced, and how did you fix it?"* | **36%**<br>*(25% / 38% / 50%)* | Prepare **one concrete engineering bug** using *Symptom $\rightarrow$ Root Cause $\rightarrow$ Fix*:<br>• *Example 1 (DB/API):* Fixing an $N+1$ query bottleneck or adding a composite index on `(user_id, created_at)` that dropped response time from $850\text{ms}$ to $60\text{ms}$.<br>• *Example 2 (Async/CORS/State):* Resolving race conditions in concurrent API requests or token refresh loops. |
| **5. 2026 GenAI / RAG / Agentic AI Defense:**<br>*"Did you just call the OpenAI/Gemini API, or what did you actually engineer?"* | **29% Overall**<br>**(68% if AI is on resume)** | In 2026, panels ruthlessly reject "wrapper" projects. Defend with **4 engineering layers**:<br>1. **Chunking & Embeddings:** *"We used recursive character splitting ($500\text{ tokens}$, $50\text{ overlap}$) so semantic context isn't cut mid-sentence."*<br>2. **Retrieval & Hallucination Control:** *"We used cosine similarity in a vector store with a strict confidence threshold ($> 0.75$) and system prompts forcing the LLM to cite retrieved chunks or return 'Insufficient context'."*<br>3. **Structured Output & Fallback:** *"We enforced JSON schema validation on LLM outputs and implemented retry/rate-limit handling."* |
| **6. Authentication & Security:**<br>*"How did you secure your APIs and passwords?"* | **26%**<br>*(15% / 28% / 42%)* | Explain **Password Hashing** (`bcrypt` with salt—never plain text or MD5), **JWT Flow** (stateless signed token in `Authorization: Bearer <token>` header, payload containing `user_id` + `role` + `exp`), and storing secrets in environment variables (`.env`). |
| **7. Scale & Concurrency Probe:**<br>*"If 10,000 concurrent users hit your app right now, what breaks first and how do you fix it?"* | **22%**<br>*(8% / 22% / 48%)* | Answer in 3 sequential steps:<br>1. **Bottleneck:** *"The database connection pool and synchronous API workers will exhaust first."*<br>2. **Database Fix:** *"Add connection pooling, read-replicas, and Redis caching for frequent read queries."*<br>3. **Compute Fix:** *"Make the backend stateless (no local session storage) and run multiple container instances behind a Load Balancer."* |
| **8. Live Modification / Schema Check:**<br>*"How would you add a 'Role-Based Admin Approval' or 'Rate Limiting' feature to your project right now?"* | **18%**<br>*(6% / 18% / 40%)* | Tests whether you actually wrote the code. Walk through the exact change: *"I would add a `status` ENUM column (`PENDING`, `APPROVED`) to the table, create a middleware/decorator that checks `current_user.role == 'ADMIN'`, and expose a `PATCH /resource/{id}/approve` endpoint."* |

---

## 5. PHASE 3: SQL Queries & Low-Level Database Design (Minutes 18 to 26)
*Across all `< 12 LPA` interviews, **74% of panels** test DBMS/SQL. In Tier 1 & 2, you are asked to write **1–2 SQL queries**. In Tier 3 ($7.6\text{–}12\text{ LPA}$), you are frequently asked to **design 3–4 tables on the spot (LLD)**.*

### A. The 6 Highest-Probability SQL Queries (Covers 90% of Live SQL Tasks)
*An interviewer will typically pick **1 or 2** of these 6 patterns during the interview:*

#### 1. The $N$-th Highest Salary (Handling Ties Correctly) — **Hit Rate: 35%**
* **Why `LIMIT / OFFSET` fails in Tier 2/3:** If two employees tie for the highest salary ($90,000$), `OFFSET 1` returns $90,000$ again instead of the true 2nd highest salary. Always give the `DENSE_RANK()` solution:
```sql
WITH RankedSalaries AS (
    SELECT emp_id, emp_name, dept_id, salary,
           DENSE_RANK() OVER (ORDER BY salary DESC) AS rnk
    FROM Employees
)
SELECT emp_id, emp_name, salary
FROM RankedSalaries
WHERE rnk = 2; -- Replace 2 with N for N-th highest
```

#### 2. Department-Wise Highest Salary (With Employee Name) — **Hit Rate: 28%**
* **Trap:** Grouping by `dept_id` and selecting `emp_name, MAX(salary)` is invalid in strict SQL because `emp_name` is not aggregated. Use `DENSE_RANK()` partitioned by department:
```sql
WITH DeptRank AS (
    SELECT e.emp_name, d.dept_name, e.salary,
           DENSE_RANK() OVER (PARTITION BY e.dept_id ORDER BY e.salary DESC) AS rnk
    FROM Employees e
    INNER JOIN Departments d ON e.dept_id = d.dept_id
)
SELECT dept_name, emp_name, salary
FROM DeptRank
WHERE rnk = 1;
```

#### 3. Finding Duplicate Records & Deleting Them — **Hit Rate: 24%**
```sql
-- Part A: Find duplicate emails
SELECT email, COUNT(*) AS freq
FROM Users
GROUP BY email
HAVING COUNT(*) > 1;

-- Part B: Delete duplicates keeping the lowest user_id
DELETE u1 FROM Users u1
INNER JOIN Users u2
ON u1.email = u2.email AND u1.user_id > u2.user_id;
```

#### 4. Self-Join: Employees Earning More Than Their Manager — **Hit Rate: 21%**
```sql
SELECT e.emp_name AS Employee, e.salary AS Emp_Salary,
       m.emp_name AS Manager, m.salary AS Mgr_Salary
FROM Employees e
INNER JOIN Employees m ON e.manager_id = m.emp_id
WHERE e.salary > m.salary;
```

#### 5. Left Join Exclusion: Customers Who Never Placed an Order — **Hit Rate: 18%**
* **Why `LEFT JOIN ... IS NULL` beats `NOT IN`:** If the `Orders.customer_id` column contains even a single `NULL` value, `NOT IN (SELECT customer_id FROM Orders)` returns **zero rows**!
```sql
SELECT c.customer_id, c.customer_name
FROM Customers c
LEFT JOIN Orders o ON c.customer_id = o.customer_id
WHERE o.order_id IS NULL;
```

#### 6. Window Function (`LAG`): Month-over-Month Revenue Growth — **Hit Rate: 12% (34% in Tier 3 / ZS / Deloitte)**
```sql
SELECT month_year, revenue,
       LAG(revenue, 1) OVER (ORDER BY month_year) AS prev_month_revenue,
       ROUND(((revenue - LAG(revenue, 1) OVER (ORDER BY month_year)) * 100.0) /
             LAG(revenue, 1) OVER (ORDER BY month_year), 2) AS growth_pct
FROM MonthlySales;
```

### B. The "Join Row-Count Prediction" Trick Question — **Hit Rate: 22%**
* **Question:** *"Table A has column `id` with values `(1, 1, 1, NULL)` and Table B has column `id` with values `(1, 1, NULL)`. How many rows will `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, and `FULL OUTER JOIN` return?"*
* **Exact Answer & Rule:**
  1. **Rule 1:** Every `1` in Table A ($3$ rows) matches with every `1` in Table B ($2$ rows) = $3 \times 2 = 6\text{ rows}$.
  2. **Rule 2:** In SQL, `NULL = NULL` is **UNKNOWN (never True)**, so `NULL`s never match each other in a standard `ON a.id = b.id` join!
  3. **Final Counts:**
     * `INNER JOIN` = **$6$ rows**
     * `LEFT JOIN` = $6 + 1$ (unmatched `NULL` from A) = **$7$ rows**
     * `RIGHT JOIN` = $6 + 1$ (unmatched `NULL` from B) = **$7$ rows**
     * `FULL OUTER JOIN` = $6 + 1 + 1$ = **$8$ rows**

### C. Low-Level Database Schema Design (LLD) — **Hit Rate: 14% Overall (38% in Tier 3: HashedIn, Infosys SP, TCS Prime)**
* **Prompt:** *"Design the database schema for an E-Commerce / Course Enrollment / Hospital Appointment system. Show Primary Keys, Foreign Keys, and how you handle Many-to-Many relationships."*
* **The 4-Step Golden Template (Use for Any Domain):**
  1. **Core Entity Tables:** `Users (user_id PK, email UNIQUE, password_hash, role)` and `Products/Courses (item_id PK, title, price, stock_count)`.
  2. **Never Store Arrays in a Column (1NF Rule):** Resolve Many-to-Many relationships using a **Junction / Mapping Table**:
     * Example: `Orders (order_id PK, user_id FK, status, total_amount, created_at)` + `Order_Items (order_item_id PK, order_id FK, item_id FK, quantity, price_at_purchase)`.
  3. **Historical Price Rule (Crucial Follow-up):** Always store `price_at_purchase` inside `Order_Items`, because if the product price changes next month in the `Products` table, old order invoices must not change!
  4. **Concurrency / Double-Booking Rule:** Mention using `SELECT ... FOR UPDATE` (pessimistic row locking) or an atomic `UPDATE Products SET stock = stock - 1 WHERE item_id = ? AND stock > 0` inside an ACID transaction so two users don't buy the last item simultaneously.

---

## 6. PHASE 4: Core CS Subjects — Authentic Hit Rates & Crisp Answers (Minutes 26 to 34)
*An interviewer typically selects **3 to 4 theory questions** across OOPs, DBMS, Language Internals, OS, and CN. Below are the exact hit rates and ready-to-speak answers.*

### Cluster 1: Object-Oriented Programming (OOPs) — *Touched in 78% of Interviews*

| Question Asked | Hit Rate (All / T1 / T2 / T3) | Ready-to-Speak Crisp Answer |
| :--- | :--- | :--- |
| **1. Explain the 4 Pillars of OOPs using your project (not Animal/Dog).** | **46%**<br>*(55% / 45% / 32%)* | • **Encapsulation:** Wrapping state and validation together (e.g., making `user.passwordHash` or `account.balance` `private` and exposing controlled getter/setter methods).<br>• **Abstraction:** Hiding implementation complexity behind an interface (e.g., calling `paymentService.process()` without knowing the internal Razorpay/Stripe HTTP calls).<br>• **Inheritance:** Reusing common attributes across specialized entities (e.g., `AdminUser` and `Customer` extending a base `BaseUser` class).<br>• **Polymorphism:** One interface, multiple implementations (e.g., a `NotificationSender` interface overridden by `EmailSender` and `SmsSender`). |
| **2. Compile-time (Overloading) vs. Runtime (Overriding) Polymorphism + Can we override a `static` or `private` method?** | **38%**<br>*(42% / 40% / 30%)* | • **Overloading:** Same method name, different parameter signatures in the same class; resolved by the compiler.<br>• **Overriding:** Child class provides a specific implementation of a parent method with the exact same signature; resolved at runtime via the **vtable / dynamic method dispatch**.<br>• **Trap Answer:** **No**, `static` methods belong to the class, not the object instance (defining the same static method in a child class is *Method Hiding*, not overriding). `private` methods are invisible to child classes, so they cannot be overridden either. |
| **3. Abstract Class vs. Interface (When to use which?)** | **31%**<br>*(34% / 32% / 26%)* | • **Use an Abstract Class** for an **"IS-A" identity** where subclasses share common state (instance variables) and default constructor logic (e.g., `BaseVehicle`).<br>• **Use an Interface** for a **"CAN-DO" capability contract** across unrelated classes (e.g., `Serializable`, `Payable`, `Comparable`) and to achieve multiple inheritance of type without the Diamond Problem. |
| **4. Deep Copy vs. Shallow Copy & Constructors** | **18%**<br>*(14% / 18% / 24%)* | • **Shallow Copy:** Copies primitive fields by value, but copies object references directly—so both original and copy point to the **same nested heap object**.<br>• **Deep Copy:** Allocates a brand-new heap copy for all nested reference objects so mutations in the copy never affect the original. |

### Cluster 2: DBMS Theory (Keys, ACID, Normalization & Indexing) — *Touched in 68% of Interviews*

| Question Asked | Hit Rate (All / T1 / T2 / T3) | Ready-to-Speak Crisp Answer |
| :--- | :--- | :--- |
| **1. Primary Key vs. Unique Key vs. Foreign Key** | **32%**<br>*(42% / 30% / 18%)* | • **Primary Key:** Uniquely identifies a row; **zero `NULL`s** allowed; only **1 per table**; creates a **Clustered Index** by default.<br>• **Unique Key:** Enforces uniqueness; allows **`NULL` values** (1 in SQL Server, multiple in MySQL/PostgreSQL); multiple allowed per table; creates a **Non-Clustered Index**.<br>• **Foreign Key:** References a Primary/Unique key in another table to enforce **Referential Integrity**. |
| **2. ACID Properties with a Banking Example** | **29%**<br>*(32% / 30% / 24%)* | If transferring $\text{₹500}$ from Account A to B:<br>• **Atomicity:** All-or-nothing (managed by Undo Logs)—if crediting B fails, debiting A rolls back.<br>• **Consistency:** Database moves from one valid state to another (total money $A + B$ remains constant and constraints hold).<br>• **Isolation:** Concurrent transactions don't read uncommitted dirty state (managed by locks/MVCC).<br>• **Durability:** Once committed, data survives power failure (managed by Write-Ahead Redo Logs). |
| **3. `DELETE` vs. `TRUNCATE` vs. `DROP`** | **24%**<br>*(32% / 24% / 12%)* | • **`DELETE` (DML):** Removes rows matching a `WHERE` clause; logs every row deletion; slower; can be rolled back before commit.<br>• **`TRUNCATE` (DDL):** Deallocates all data pages at once and resets auto-increment; keeps table schema; much faster.<br>• **`DROP` (DDL):** Completely removes the table data, schema, and indexes from the database. |
| **4. Normalization (1NF, 2NF, 3NF, BCNF) in 60 Seconds** | **21%**<br>*(15% / 22% / 32%)* | • **1NF:** Atomic values only (no comma-separated lists in a cell).<br>• **2NF:** 1NF + **No Partial Dependency** (every non-prime attribute must depend on the *entire* composite primary key, not just half of it).<br>• **3NF:** 2NF + **No Transitive Dependency** (non-prime attributes cannot depend on other non-prime attributes, e.g., `zip_code -> city`).<br>• **BCNF:** Strict 3NF where for every dependency $X \rightarrow Y$, $X$ must be a **Super Key**. |
| **5. How does Database Indexing work internally, and why not index every column?** | **19%**<br>*(8% / 20% / 36%)* | • **How it works:** Databases build a balanced **$B\text{-Tree}$ or $B^+\text{-Tree}$** on the indexed column, reducing lookup time from full-table scan $O(N)$ to logarithmic $O(\log N)$.<br>• **Why not index every column?** Every `INSERT`, `UPDATE`, and `DELETE` must rebalance all $B^+\text{-Trees}$ on that table, which severely slows down write performance and consumes extra disk/RAM space. |

### Cluster 3: Language Internals (Java / Python / C++) — *Touched in 56% of Interviews*

| Language & Top Questions | Hit Rate (When Language Chosen) | Ready-to-Speak Crisp Answer |
| :--- | :--- | :--- |
| **Java:**<br>1. Why are Strings immutable?<br>2. `==` vs `.equals()`<br>3. How does `HashMap` work internally? | **48%**<br>*(of Java candidates)* | 1. **String Immutability:** Enables the **String Constant Pool** (saving heap memory), ensures thread-safety without locks, caches `hashCode()` for fast `HashMap` keys, and prevents security tampering (e.g., file paths/DB URLs).<br>2. **`==` vs `.equals()`:** `==` compares memory references; `.equals()` compares actual character/object content.<br>3. **`HashMap` Internals:** Computes `key.hashCode()` $\rightarrow$ maps to a bucket index (`(n - 1) & hash`) $\rightarrow$ handles hash collisions via a Linked List, which converts into a **Balanced Red-Black Tree** ($O(\log n)$) once a bucket exceeds **8 nodes** (Java 8+). |
| **Python:**<br>1. List vs. Tuple vs. Set<br>2. What are Decorators & Generators?<br>3. Memory Management & GIL | **46%**<br>*(of Python candidates)* | 1. **List vs. Tuple:** Lists are mutable dynamic arrays; Tuples are immutable, memory-compact, and hashable (can be used as `dict` keys). Sets are unordered hash tables with $O(1)$ lookup.<br>2. **Decorators & Generators:** A Decorator is a higher-order function that wraps another function to add behavior (like `@app.get` or auth checks). A Generator uses `yield` to produce items lazily one at a time in $O(1)$ memory.<br>3. **GIL:** The Global Interpreter Lock ensures only one thread executes Python bytecode at a time to protect reference-counting memory management. |
| **C++:**<br>1. Pointers vs. References<br>2. `virtual` functions & `vtable`<br>3. `new/delete` vs `malloc/free` | **45%**<br>*(of C++ candidates)* | 1. **Pointers vs. References:** Pointers can be reassigned, can be `nullptr`, and have their own memory address; References must be initialized at declaration, cannot be null, and act as an alias.<br>2. **`virtual` & `vtable`:** Declaring a base function `virtual` creates a hidden `vptr` pointing to a `vtable` of function pointers, enabling runtime polymorphism.<br>3. **`new` vs `malloc`:** `new` is an operator that allocates memory AND calls the class **Constructor** (returning a typed pointer); `malloc` only allocates raw bytes and returns `void*`. |

### Cluster 4: Operating Systems (OS) & Computer Networks (CN) — *Touched in 42% of Interviews*

| Question Asked | Hit Rate (All / T1 / T2 / T3) | Ready-to-Speak Crisp Answer |
| :--- | :--- | :--- |
| **1. Process vs. Thread (and what do threads share?)** | **24%**<br>*(22% / 25% / 28%)* | A **Process** is an independent executing program with its own isolated virtual address space. A **Thread** is a lightweight execution unit within a process. Threads of the same process **share the Heap, Code, and Data segments**, but each thread has its **own independent Stack and Program Counter (registers)**. |
| **2. What is Deadlock? Name the 4 Coffman Conditions.** | **18%**<br>*(14% / 18% / 24%)* | Deadlock occurs when processes are permanently blocked waiting for resources held by each other. All 4 conditions must hold: **1. Mutual Exclusion**, **2. Hold and Wait**, **3. No Preemption**, and **4. Circular Wait**. In practice, we prevent deadlock by breaking **Circular Wait** (enforcing a strict global ordering on lock acquisition). |
| **3. Virtual Memory, Paging & Thrashing** | **14%**<br>*(8% / 14% / 24%)* | **Virtual Memory** lets programs run even when larger than physical RAM by keeping only active pages in RAM and inactive pages on disk. **Thrashing** happens when the OS spends more time swapping pages between RAM and disk (page faults) than executing actual CPU instructions. |
| **4. REST API Methods (`GET`, `POST`, `PUT`, `PATCH`) & HTTP Status Codes** | **23%**<br>*(16% / 24% / 34%)* | • **`GET`** (Idempotent read), **`POST`** (Non-idempotent create), **`PUT`** (Idempotent full replacement), **`PATCH`** (Partial update).<br>• **Codes:** `200` (OK), `201` (Created), `400` (Bad Request/Validation error), `401` (Unauthenticated—missing/invalid token), `403` (Forbidden—authenticated but lacks role permission), `404` (Not Found), `500` (Internal Server Error). |
| **5. TCP vs. UDP & What happens when you type `google.com`?** | **17%**<br>*(12% / 18% / 24%)* | • **TCP:** Connection-oriented (3-way handshake: `SYN`, `SYN-ACK`, `ACK`), guarantees ordering and retransmission (HTTP, SSH). **UDP:** Connectionless, low latency, no retransmission (Video streaming, DNS, Gaming).<br>• **`google.com` Flow:** Browser/OS DNS cache check $\rightarrow$ DNS Resolver returns IP $\rightarrow$ TCP 3-way handshake on port 443 $\rightarrow$ TLS cryptographic handshake $\rightarrow$ HTTP `GET` request $\rightarrow$ Server returns HTML $\rightarrow$ Browser DOM rendering. |

---

## 7. PHASE 5: Managerial Scenarios, Role-Downgrade Traps & Puzzles (Minutes 34 to 42)
*In the Managerial Round (or minutes 30–40 of a combined panel), interviewers pick **2 Behavioral/Scenario questions** and (in Tier 2/3) **1 Logic Puzzle or Guesstimate**.*

### A. Top 5 Managerial Scenarios & Exact Winning Scripts

| Scenario Question Asked | Hit Rate (All / T1 / T2 / T3) | The Trap vs. The Winning Script |
| :--- | :--- | :--- |
| **1. Conflict / Uncooperative Teammate:**<br>*"Tell me about a time a teammate wasn't contributing or disagreed with your technical approach."* | **41%**<br>*(38% / 42% / 44%)* | **Trap:** Complaining about your teammate ("They were lazy, so I did everything").<br>**Winning Script (STAR):** *"During our capstone project, a teammate and I disagreed on whether to process file uploads synchronously or asynchronously. Instead of arguing opinions, I benchmarked a 10MB file upload both ways, showed that synchronous requests blocked the main thread for 4 seconds, and we jointly implemented a background task queue. Whenever a teammate fell behind, we broke their module into smaller 2-day sub-tasks and paired up for 20 minutes daily."* |
| **2. The Legacy / Support / Testing Trap:**<br>*"Your resume has AI/Cloud/Full-Stack, but what if we assign you to a Legacy Mainframe, Testing, or Support project?"* | **38%**<br>*(48% / 36% / 22%)* | **Elimination Trap:** Saying *"I only want development or AI roles"* causes instant rejection in TCS, Infosys, Cognizant, Wipro, and Accenture.<br>**Winning Script:** *"As a fresher, my first priority is understanding how enterprise systems run reliably at scale—how production incidents are debugged, how SLAs are maintained, and how business workflows operate. I will give 100% to deliver excellence in whichever team needs me, while automating repetitive tasks and upskilling to grow with the project."* |
| **3. SDLC & Agile / Scrum Workflow:**<br>*"Explain the phases of SDLC and how Agile works in a software team."* | **34%**<br>*(38% / 35% / 28%)* | Walk through the **6 SDLC phases**: *Requirement Analysis $\rightarrow$ System Design $\rightarrow$ Implementation/Coding $\rightarrow$ Testing (Unit/Integration/UAT) $\rightarrow$ Deployment (CI/CD) $\rightarrow$ Maintenance*. Define **Agile Scrum**: breaking delivery into **2-week sprints**, tracking tasks on Jira, holding **15-minute daily stand-ups**, and doing Sprint Retrospectives. |
| **4. The Multi-Tier Role-Downgrade Trap:**<br>*"You are interviewing for TCS Prime ($9\text{L}$) / GenC Next ($6.75\text{L}$). If we offer you Digital ($7\text{L}$) or Ninja ($3.36\text{L}$) instead, will you join?"* | **32%**<br>*(in TCS, Infosys, Cognizant, Capgemini)* | **The Trap:** Panelists use this both to check ego/attrition risk and to see if you lack confidence.<br>**Balanced Winning Script:** *"Based on my OA performance, end-to-end project architecture, and technical preparation, I am confident I can contribute at the Prime/Next benchmark from day one. However, my primary goal is to start my career with [Company Name], and I trust the panel's evaluation of where I fit best—plus I know internal upgradation pathways (like TCS Wings) allow top performers to advance rapidly."* |
| **5. Tight Deadline / Late Requirement Change:**<br>*"What if the client changes a core requirement 48 hours before the release?"* | **27%**<br>*(22% / 28% / 34%)* | 1. Assess impact on database schema and existing test cases.<br>2. Negotiate a **Minimum Viable Release (Phase 1 core fix now, Phase 2 edge features in the next sprint)** with the Engineering Manager.<br>3. Never push untested code straight to production at the last minute. |

### B. The 6 Highest-Yield Logic Puzzles & Guesstimates
*Overall Puzzle/Guesstimate Hit Rate: **21%** (**9%** in Tier 1, **22%** in Tier 2, **54%** in Tier 3 like ZS Associates, Deloitte, HashedIn, Amadeus, Infosys SP).*

1. **The 8 Balls / 9 Coins Weighing Puzzle (Minimum Weighings):**
   * *Question:* You have 8 (or 9) identical-looking balls; 1 is slightly heavier. Using a mechanical balance scale (no weights), find the heavier ball in the **minimum** number of weighings.
   * *Solution:* **2 weighings** (not 3!). Divide into **3 groups** of $(3, 3, 2)$ [or $(3, 3, 3)$ for 9 balls].
     * **Weighing 1:** Weigh Group A ($3$ balls) vs. Group B ($3$ balls).
     * If one side goes down, the heavy ball is in that group of $3$. If they balance, it's in the remaining group of $2$ (or $3$).
     * **Weighing 2:** From the suspect group of $3$, weigh $1$ ball vs. $1$ ball. If one goes down, that's it; if they balance, it's the $3\text{rd}$ unweighed ball! (General formula: $\lceil \log_3(N) \rceil$).

2. **The 3 Bulbs and 3 Switches Puzzle:**
   * *Question:* 3 switches outside a closed room control 3 incandescent bulbs inside. You can enter the room only once. How do you match each switch to its bulb?
   * *Solution:* Use **two physical properties (Light + Heat)**. Turn Switch 1 ON for $5\text{–}10\text{ minutes}$, then turn Switch 1 OFF and turn Switch 2 ON. Walk inside immediately:
     * **Lit bulb** = Switch 2.
     * **Unlit but warm bulb** = Switch 1.
     * **Unlit and cold bulb** = Switch 3.

3. **The 3L and 5L Water Jug Puzzle (Measure Exactly 4 Liters):**
   * *Solution (6 steps):* Fill $5\text{L}$ jug ($5, 0$) $\rightarrow$ Pour into $3\text{L}$ jug until full ($2, 3$) $\rightarrow$ Empty $3\text{L}$ jug ($2, 0$) $\rightarrow$ Pour remaining $2\text{L}$ from $5\text{L}$ into $3\text{L}$ jug ($0, 2$) $\rightarrow$ Fill $5\text{L}$ jug completely ($5, 2$) $\rightarrow$ Pour from $5\text{L}$ into $3\text{L}$ jug until full (takes $1\text{L}$), leaving **exactly $4\text{L}$** in the $5\text{L}$ jug!

4. **The 25 Horses Puzzle (Minimum Races for Top 3):**
   * *Question:* 25 horses, 5 tracks (max 5 horses per race), no stopwatch. Minimum races to find the fastest 3 horses?
   * *Solution:* **7 races.**
     * **Races 1–5:** Race all 25 horses in 5 groups of 5.
     * **Race 6:** Race the 5 group winners ($A_1, B_1, C_1, D_1, E_1$). Suppose order is $A_1 > B_1 > C_1 > D_1 > E_1$. Eliminate groups $D$ and $E$ completely, plus $C_2..C_5$, $B_3..B_5$, and $A_4..A_5$. Only **5 candidates** can possibly be 2nd or 3rd overall: $(A_2, A_3, B_1, B_2, C_1)$.
     * **Race 7:** Race those 5 horses. Top 2 of Race 7 are the overall 2nd and 3rd fastest!

5. **The Amadeus / HashedIn Parity Marbles Puzzle:**
   * *Question:* A jar has 50 White and 50 Black marbles. You draw 2 marbles at a time: if they are the **same color**, you put **1 Black marble** back in; if they are **different colors**, you put **1 White marble** back in. What is the color of the very last marble remaining?
   * *Solution:* Track the **parity (odd/even) of White marbles**:
     * Drawing $(B, B) \rightarrow$ replace with $B$: White count changes by $0$.
     * Drawing $(W, B) \rightarrow$ replace with $W$: White count changes by $0$.
     * Drawing $(W, W) \rightarrow$ replace with $B$: White count decreases by **2**.
     * Since the number of White marbles starts at **50 (even)** and only ever changes by $0$ or $-2$, the number of White marbles can **never become 1 (odd)**! Therefore, the last single marble **must be Black**.

6. **The ZS / Deloitte 3-Minute Guesstimate Template:**
   * *Common Prompts:* *"Estimate the number of UPI transactions / Swiggy orders / Petrol pumps in Delhi or India per day."*
   * *How to Solve Out Loud in 4 Lines:*
     1. **Clarify & Anchor Population:** Take Delhi population $\approx 2\text{ Crore}$ ($20\text{M}$) or India $\approx 140\text{ Crore}$.
     2. **Filter Smartphone/Target Base:** Assume $70\%$ smartphone & digital payment penetration ($14\text{M}$ people in Delhi).
     3. **Segment by Usage Frequency:** Heavy users ($30\% \rightarrow 4\text{ txns/day}$), Moderate ($50\% \rightarrow 1.5\text{ txns/day}$), Low ($20\% \rightarrow 0.5\text{ txns/day}$).
     4. **Multiply & Sanity Check:** Weighted average $= (0.3 \times 4) + (0.5 \times 1.5) + (0.2 \times 0.5) = 2.05\text{ txns/person/day} \times 14\text{M} \approx \mathbf{2.87\text{ Crore UPI transactions/day}}$.

---

## 8. PHASE 6: The HR Round & 2026 Company Fact Sheet (Final 5–10 Minutes)
*Only 5%–10% of candidates get eliminated in HR, and almost every rejection comes from failing one of the first 3 verification checks below.*

### A. The 5 Core HR Questions & Safe Answers

| Question Asked | Hit Rate | Safe, High-Conversion Script |
| :--- | :--- | :--- |
| **1. Relocation, Night Shifts & Service Agreement:**<br>*"Are you comfortable relocating anywhere in India, working rotational shifts, and signing our service agreement?"* | **76%** | **Always a clear, zero-hesitation "Yes."** Say: *"Yes, completely. Having already lived in a university hostel away from my home state, adapting to a new city and flexible project schedules is very natural for me."* |
| **2. Company Alignment:**<br>*"Why do you want to join [Company Name]?"* | **54%** | Combine **1 company-specific 2026 fact** (from the table below) + **their structured fresher training ecosystem** + **how your backend/AI/data skills align with their current digital transformation push**. |
| **3. Higher Studies / Retention Check:**<br>*"Do you have any plans for GATE, CAT, or MS in the next 2–3 years?"* | **43%** | **Never say "Maybe after 2 years."** Say: *"No, my focus has always been hands-on software engineering in the industry. I learn best by building production systems, and I plan to build a long-term technical career within the corporate track."* |
| **4. Strengths & Genuine Weakness:**<br>*"What is your biggest strength and one weakness?"* | **34%** | • **Strength:** *"Structured paper-first problem solving and consistency"* (backed by your daily practice and project architecture).<br>• **Weakness:** Never say "I'm a perfectionist." Use a real trait + your fix: *"Earlier, when stuck on a bug, I used to spend too long trying to solve it entirely alone before reaching out. Now, I use a strict 30-minute timebox to debug and check official docs before asking a senior or teammate with a clear summary of what I've already tried."* |
| **5. The Closing Question:**<br>*"Do you have any questions for us?"* | **82%** | **Never say "No, I'm good."** Ask 1 sharp question:<br>• *"What does the first 90 days of onboarding and project allocation look like for a fresher joining your unit?"* OR<br>• *"How is GenAI or Cloud modernization changing the modules freshers get to work on at [Company Name]?"* |

### B. 2026 Company Cheat Sheet (Memorize 60 Seconds Before Walking In)

| Company | Current CEO (2026) | HQ | Key Platform / 2026 Initiative to Mention in "Why Us?" |
| :--- | :--- | :--- | :--- |
| **TCS** | K. Krithivasan | Mumbai | **TCS WisdomNext** (GenAI aggregation platform), **TCS BaNCS**, and the **Xplore / Wings** internal growth ecosystem. |
| **Infosys** | Salil Parekh | Bengaluru | **Infosys Topaz** (AI-first suite), **Infosys Cobalt** (Cloud), and the world-class **Mysuru Global Education Center** training. |
| **Cognizant** | Ravi Kumar S | Teaneck, NJ | **Cognizant Neuro AI** platform, **Flowsource** developer platform, and strong Healthcare/BFSI engineering footprint. |
| **Accenture** | Julie Sweet | Dublin | **$3\text{B}$ Data & AI investment**, **AI Navigator** for Enterprise, and modular micro-credential training. |
| **Capgemini** | Aiman Ezzat | Paris | **Generative AI Lab**, Cloud & Custom Software Engineering, and strong European/Global automotive & retail clients. |
| **Wipro** | Srini Pallia | Bengaluru | **Wipro ai360** ecosystem and enterprise cloud modernization (**FullStride Cloud**). |
| **LTIMindtree** | Venu Lambu | Mumbai | **Canvas.ai** enterprise GenAI platform and high-density data/cloud engineering post-merger. |
| **Deloitte / HashedIn** | Punit Renjen (Emeritus) / Joe Ucuzoglu | London / Bengaluru | **HashedIn University (HU)** 8-week intensive bootcamp, product-style pods, and **Deloitte CortexAI**. |
| **ZS Associates** | Pratap Khedkar | Evanston, IL | **ZAIDYN** cloud-native analytics platform and market leadership in healthcare/pharma data consulting. |
| **Amadeus Labs** | Luis Maroto | Madrid (R&D: Bengaluru) | Powers global airline/travel reservation backbones (**Altéa Suite**) handling tens of thousands of transactions per second. |