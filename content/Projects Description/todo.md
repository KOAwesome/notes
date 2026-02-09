### **1️⃣ One FAILURE story (MOST IMPORTANT)**

  

Interviewers trust failure more than success.

  

If you have **one real incident**, share:

- Glue job failed / data drift / wrong joins
    
- What broke
    
- How you debugged (logs, Spark UI, metrics)
    
- What you changed permanently
    

  

Example (you don’t need to send code, just describe):

  

> “A window join caused silent duplication, increasing row counts by 12%. I caught it via profile comparison and fixed it by tightening temporal conditions and repartitioning.”

  

If you want, you can send **just the story**, not screenshots.

---

### **2️⃣ Glue + Spark runtime details (only bullets)**

  

Not code. Just facts.

  

If you can answer these, you’re set:

- Glue version (3.0 / 4.0)
    
- Worker type (G.1X / G.2X)
    
- Avg data size (GBs)
    
- Runtime (mins)
    
- Retry strategy
    

  

You can reply in **5 bullets**. That’s it.

---

### **3️⃣ CI/CD or orchestration (if ANY involvement)**

  

Even small involvement counts:

- Bitbucket pipelines?
    
- Glue job params via config?
    
- Step Functions / Airflow?
    
- Manual vs automated deploy?
    

  

If you touched even **one part**, mention it.

---

## **What you should NOT share anymore**

  

❌ Full code dumps

❌ More screenshots

❌ Copilot summaries

❌ “Original code vs my changes” explanations

  

At this point, more info = noise.



## **What OPTIONAL extras would level this up HARD**

  

### **1️⃣ ONE failure / incident story (MOST valuable)**

  

Give me **one real incident**, even roughly:

- Glue job failed / data wrong / downstream broke
    
- What triggered it
    
- What YOU investigated
    
- What YOU fixed or changed
    

  

Doesn’t need code. Even a paragraph is enough.

  

👉 This lets me:

- Craft **perfect behavioral answers**
    
- Turn you into “production-tested engineer”, not just “good coder”
    

---

### **2️⃣ ONE Spark performance decision you made**

  

Example prompts (pick any one you remember):

- “Why did you repartition here?”
    
- “Why window instead of groupBy?”
    
- “How did you avoid skew / OOM / long shuffle?”
    

  

Even if it was small.

  

👉 This lets me:

- Arm you for **system design + Spark deep dives**
    
- Stop interviewers from poking holes
    

---

### **3️⃣ ONE thing you were NOT allowed to change (constraints)**

  

Example:

- Schema fixed by client
    
- Legacy logic you had to respect
    
- SLA / regulatory constraint
    
- Cost cap (Athena / Glue)
    

  

👉 This lets me:

- Frame you as a **real-world engineer**
    
- Not someone working in a perfect sandbox
    

---

## **What you should NOT send**

  

❌ Full source code

❌ Screenshots of confidential logic

❌ Company names / client identifiers

  

You don’t need to risk anything. High-level descriptions are enough.

---

## **If you don’t send anything more**

  

Even then, I can:

- Simulate **hard DE interviews**
    
- Write **resume bullets that don’t undersell you**
    
- Prepare **referral-ready explanations**
    

  

But if you send **just ONE of the three above**, I can tailor this to:

  

> “This candidate has already survived production complexity.”

---

### **Your move (answer with just a number or short text):**

  

1️⃣ Incident story

2️⃣ Spark performance decision

3️⃣ Constraint you worked under

or

👉 “Proceed with what you have