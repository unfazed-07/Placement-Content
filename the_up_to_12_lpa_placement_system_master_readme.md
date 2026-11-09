# The Up-to-12 LPA Placement System — Master README

**Target Bracket:** Base IT Services (TCS Ninja, Infosys SE, Cognizant GenC, Wipro, Accenture ASE), Differential Tech Roles (TCS Digital, Infosys DSE, Cognizant GenC Pro/Next, Capgemini Exceller), and Prime / Enterprise Product & Consulting Firms (TCS Prime, Infosys SP, Deloitte USI, HashedIn, ZS Associates, Amadeus, IBM, Oracle, Barclays, Juspay, ION Group) — **3.36 LPA to 12.0 LPA**.

This repository contains **three hyper-targeted preparation blueprints** designed to eliminate random preparation and cover the exact patterns, questions, and evaluation filters used across campus placements up to 12 LPA.

---

## 1. How Campus Placements Actually Work (The Under-12 LPA Reality)

Most students fail or burn out during campus placements because they either grind 400+ random FAANG-level competitive programming problems or memorize textbook definitions without knowing how to write clean $O(n)$ code on paper, defend resume projects, or survive automated filters. Because campus recruiters evaluate thousands of candidates across tight 30-to-45-minute windows, **90% of the evaluation follows a predictable, mathematically bounded funnel**:

* **Stage 1 — The Non-DSA OA Eliminators (Where 70%–80% Get Cut):** Before an interviewer ever sees your resume, companies filter out the majority of applicants using Quantitative Aptitude, Bitwise/Recursion Pseudocode traps (Capgemini, Accenture, Infosys), Game-Based Aptitude (Capgemini, IBM, Deloitte), SHL Data/Verbal Reasoning, and AI-proctored voice assessments (Versant/SVAR).
* **Stage 2 — The Coding OA (Constraint-Driven Patterns):** Coding rounds do not invent brand-new algorithms. Input constraints ($N$) directly dictate the expected approach (e.g., $N \le 10^5$ strictly requires $O(n)$ or $O(n \log n)$ via Sliding Window, Two Pointers, HashMap, or Binary Search). Furthermore, service-based OAs heavily recycle a fixed bank of custom story-based problems alongside 2 live SQL queries.
* **Stage 3 — The 40-Minute Face-to-Face Interview Slot Budget:** In a single sitting, a panelist only has time to ask **1 to 2 live coding problems** (written on physical paper or plain Notepad in 85% of drives) and **12 to 15 non-DSA questions** across fixed time slots:
  * **Minutes 0–5 (Icebreakers & Steering):** 1 opener (*"Tell me about yourself"*) + 1 transition question. Whatever you highlight in the final sentence of your introduction dictates the next 15 minutes of the interview.
  * **Minutes 5–18 (Project & Architecture Defense — 35%–45% Weightage):** 1 end-to-end data-flow overview + 2 to 3 technical probes (individual contribution, SQL vs. NoSQL trade-offs, JWT/bcrypt security, real debugging bottlenecks, or defending GenAI/RAG pipelines beyond simple API wrappers).
  * **Minutes 18–34 (Live SQL, LLD & Core CS — ~7 Questions Total):** Panelists sample **6.5 to 8 Core CS questions** weighted heavily toward **OOPs (32%)** and **DBMS/Live SQL (30%)**, followed by **System Design/Scaling (16%)**, **Operating Systems (12%)**, and **Computer Networks (10%)**.
  * **Minutes 34–42 (Managerial, Puzzles & HR Verification):** 2 behavioral/conflict scenarios, 1 logic puzzle or guesstimate (54% hit rate in 8–12 LPA tiers), and 3 to 4 non-negotiable HR retention checks (relocation, night shifts, service agreements, legacy/support readiness, and role-downgrade traps) where a single hesitant answer triggers silent rejection.

---

## 2. Deep-Dive: What Is Inside Each of the 3 Blueprint Files

Each file in this repository locks down one complete pillar of the placement funnel:

### File 1: `tier_ranked_topic_wise_non_negotiable_dsa_questions_up_to_12_lpa.md`
* **Primary Focus:** Online Assessment Coding & Live Paper/Notepad DSA Interviews (3.5 LPA – 12 LPA).
* **How It Is Structured & What It Contains:**
  * **Section 0 (Package-Band Mapping & Compass Direction):** Maps exact problem tiers to 4 salary bands and shows how to instantly deduce the optimal algorithm from input size constraints ($N \le 20$ up to $N \le 10^{18}$).
  * **Part 1 (The 90 Core DSA Problems Across 5 Priority Tiers):** Every question includes its **Pattern Trigger**, **Brute-to-Optimal Direction**, and **Edge-Case Traps**:
    * **Tier S (18 Qs — 3.5–6 LPA Foundation):** Solves Q1 of 90% of OAs (Two Sum, Kadane's, Dutch National Flag, Sliding Window, Anagrams, Linked List Reversal/Cycle, Binary Search, Primes/GCD).
    * **Tier A (18 Qs — 6–8 LPA Differentiators):** Boyer-Moore Majority, Merge Intervals, Product Except Self, Spiral Matrix, 3Sum, Rotated Binary Search, Monotonic Stack, Tree Traversals, Merge/Quick Sort, 1D DP.
    * **Tier B (18 Qs — 8–10 LPA Evaluators):** Next Permutation, Trapping Rain Water, Koko Eating Bananas (BS on Answer), Min Stack, Tree Views/LCA/BST Validation, Heaps, Greedy Platforms, Islands, 0/1 Knapsack & Coin Change.
    * **Tier C (18 Qs — 9–10.5 LPA Specialist Shield):** Count Inversions, Minimum Window Substring, LRU Cache, Multi-Source BFS (Rotting Oranges), Graph Cycle Detection, Topological Sort, Dijkstra, Backtracking, LCS/LIS.
    * **Tier D (18 Qs — 10–12 LPA FinTech/Product Extension):** Merge $K$ Lists, Sliding Window Max (Deque), Histogram Rectangle, Book Allocation, Juspay Graph Trio, DSU/Kruskal's MST, Edit Distance, Stock DP, Tries, Base62 URL Shortener.
  * **Part 2 (The Verbatim Company OA Story Vault — 16 Qs):** Exact repeated story problems for **Accenture** (*Rat Count House, Binary String Ops, Password Checker*), **TCS** (*Vehicles & Wheels, Unique Digits, 3-Palindrome Split*), **Capgemini/Cognizant** (*Move Hashes, Minimum Discount*), and **Infosys DSE/SP** (*Next Smallest Palindrome, RPG Monster Defeat*).
  * **Part 3 (Topic-Wise Study Checklist):** All 90 problems organized across 10 core DSA topics with tier tags for progress tracking.
  * **Part 4 (Live Face-to-Face Coding Guide):** Breakdown of the 4 F2F coding buckets, the **Top 20 Live Paper/Notepad Coding Problems** (accounting for 95% of F2F slots), **10 Oral DSA Cross-Questions** (HashMap internals, Quick vs. Merge sort, BFS vs. DFS), and **6 mandatory SQL/OOP code snippets**.

### File 2: `ranked_core_cs_system_design_interview_bible_up_to_12_lpa.md`
* **Primary Focus:** Core CS Theory, Language Internals, Live SQL & System Design (LLD/HLD).
* **How It Is Structured & What It Contains:**
  * **Section 0 (The Genuine Probability Model):** Compiled from 1,500+ interview experiences, showing exact subject hit rates and question counts across Band 1 (3.5–5.5L), Band 2 (6.0–8.5L), and Band 3 (8.5–12L).
  * **Part 1 (The Top 18 Overall Interview Scenarios — 82% Coverage):** Ranked #1 to #18 across all subjects. Each scenario provides the **True Per-Interview Probability**, the **Exact Interviewer Prompt**, a **60-Second Answer Blueprint**, and the **Follow-Up Trap Defense**. Covers $N$-th Highest Salary (`DENSE_RANK`), 4 OOP Pillars mapped to projects, Polymorphism & `vtable`, SQL Join Row-Count Traps with Duplicates/`NULL`s, Abstract Class vs. Interface, ACID & Isolation Levels, Keys & Clustered Indexes, B+ Tree Indexing, Stack/Heap/String/HashMap Internals, Process vs. Thread & Mutex/Semaphore, Normalization (1NF–BCNF), Scaling from 100 to 100k Users (5-Step HLD Ladder), `DELETE`/`TRUNCATE`/`DROP` & SQL Execution Order, Deadlocks, Singleton/Factory/SOLID, Virtual Memory/Paging, `https://google.com` Network Flow, and Parking Lot LLD.
  * **Part 2 (Subject-by-Subject Ranked Question Vault):** Rapid-fire probability tables with crisp 1-line full-marks answers across all 5 pillars: **OOPs & Internals (32%)**, **DBMS & SQL (30%)**, **System Design — LLD, HLD & Security (16%)**, **Operating Systems (12%)**, and **Computer Networks (10%)**.
  * **Part 3 (The Live SQL Whiteboard Gauntlet & 3-Day Revision Plan):** The **6 exact SQL queries** you must write from memory without syntax errors, plus a 3-day pre-drive revision schedule.

### File 3: `the_complete_end_to_end_placement_interview_blueprint_12_lpa.md`
* **Primary Focus:** The Non-DSA 70% of Placements — OA Filters, Resume/Project Defense, Managerial Scenarios, Puzzles & HR.
* **How It Is Structured & What It Contains:**
  * **Section 0 & 1 (Methodology & 2026 Company Evaluation Matrix):** Built from 428 verified interview transcripts (2024–2026 batches), featuring a company-by-company breakdown (TCS, Infosys, Accenture, Capgemini, Cognizant, Deloitte/HashedIn, ZS, Oracle, Amadeus) of CTC tiers, OA filters, and primary interview deciders.
  * **Phase 0 (Surviving the Non-DSA OA Filters):** Concrete shortcuts for Bitwise XOR/`&` vs. `&&`/Recursion pseudocode traps, Game-Based Aptitude (Grid, Switch, Inductive challenges), SHL *"True / False / Cannot Say"* traps, and AI Spoken English (Versant/SVAR) fluency rules.
  * **Phase 1 & Phase 2 (Minutes 0–18 — Icebreakers & Project Deep-Dive):** Word-for-word frameworks for the 60-second opener, steering the panel, tracing end-to-end API requests, proving backend ownership, defending tech stack trade-offs, presenting a *Symptom $\rightarrow$ Root Cause $\rightarrow$ Fix* debugging story, and defending **GenAI / RAG projects** (chunking, embeddings, hallucination thresholds, schema validation).
  * **Phase 3 & Phase 4 (Minutes 18–34 — Live SQL, Schema LLD & Language Internals):** Top 6 SQL queries (including `LAG()` revenue growth), Join row-count rules, the **4-Step Golden Template for Low-Level Database Schema Design** (junction tables, historical pricing, `SELECT ... FOR UPDATE` locking), and cluster-wise Q&A for OOPs, DBMS, **Java / Python / C++ Internals**, OS, and CN.
  * **Phase 5 & Phase 6 (Minutes 34–42 — Managerial, Puzzles & 2026 HR Fact Sheet):** Word-for-word STAR scripts for teammate conflicts, the Legacy/Support/Testing trap, Agile/SDLC, and Multi-Tier Role-Downgrade checks; step-by-step solutions to the **6 Highest-Yield Logic Puzzles & Guesstimates** (8 Balls, 3 Bulbs, 3L/5L Jugs, 25 Horses, Parity Marbles, 3-Minute Guesstimate template); safe answers for the **5 Core HR Questions**; and a **2026 Company Cheat Sheet** (current CEOs, HQs, and flagship AI/Cloud initiatives).

---

## 3. How the System Maps to Your Target Salary Band

| Target Package Band | Representative Roles | What You Must Master Across the 3 Files |
| :--- | :--- | :--- |
| **Band 1: 3.36 – 5.0 LPA** *(Base Service)* | TCS Ninja, Infosys SE, Cognizant GenC, Wipro Elite, Capgemini A4, Accenture ASE | **DSA:** Tier S (18 Qs) + Part 2 OA Vault + Top 20 Live Coding.<br>**Core CS:** Ranks #1–#7, #10, #13 + Basic SQL.<br>**Blueprint:** Phase 0 OA Filters + Project Overview + HR Scripts. |
| **Band 2: 5.4 – 7.5 LPA** *(Differential Tech)* | TCS Digital, Infosys DSE, Cognizant GenC Pro/Next, Accenture AASE, Capgemini Exceller, LTIMindtree | Everything in Band 1 + **DSA:** Tier A (18 Qs).<br>**Core CS:** Ranks #8–#15 + All 6 Live SQL Gauntlet Queries.<br>**Blueprint:** Full Project Defense (GenAI/Trade-offs/Bugs) + Role-Downgrade Script. |
| **Band 3: 7.6 – 10.0 LPA** *(Prime & Consulting)* | TCS Prime, Infosys SP, Deloitte USI, HashedIn, ZS Associates, HSBC, Amadeus | Everything in Bands 1–2 + **DSA:** Tiers B & C (36 Qs).<br>**Core CS:** All Top 18 Scenarios (HLD Scaling, Design Patterns, LLD Schema).<br>**Blueprint:** Live DB Schema Design + 6 Logic Puzzles & Guesstimates. |
| **Band 4: 10.0 – 12.0 LPA** *(Enterprise Product)* | IBM, Oracle, Barclays, Juspay, ION Group, NatWest, Sabre | Everything in Bands 1–3 + **DSA:** Tier D (18 Qs — Advanced Graphs/DP/Tries).<br>**Core CS:** Full Concurrency, B+ Tree Internals, Isolation Anomalies & LLD Concurrency. |