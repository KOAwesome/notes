### Example

User A:

|date|row_number|date - rn|
|---|---|---|
|Jan 1|1|Jan 0|
|Jan 2|2|Jan 0|
|Jan 3|3|Jan 0|
|Jan 5|4|Jan 1 ❌ break|

👉 First 3 rows → same group  
👉 Jan 5 → new group







# Intermediate-Advanced (You Should Learn Next)

### 🟢 Window Frame Clauses (VERY IMPORTANT)

```
SUM(x) OVER (  ORDER BY date   ROWS BETWEEN 3 PRECEDING AND CURRENT ROW)
```

👉 Rolling windows

---

### 🟢 CTE Optimization & Recursion

```
WITH RECURSIVE
```

👉 trees, sequences

---

### 🟢 Set Operations

```
UNION, INTERSECT, EXCEPT
```

---

### 🟢 NULL Handling (Deep)

```
COALESCE, NULLIF
```

---

### 🟢 Advanced Joins


self joins, anti joins, semi joins 
```  
regexp_split_to_table(contents, '\s+') ### Split Text into Rows (Important)

```
string → multiple rows

Examples:

| DB         | Function                |
| ---------- | ----------------------- |
| PostgreSQL | `regexp_split_to_table` |
| SQL Server | `STRING_SPLIT`          |
| MySQL      | (no direct, workaround) |

👉 This is worth learning ✔ ### Regex Matching (Moderate)

Basic patterns:

```
LIKE '%abc%'        -- simpleREGEXP / ~          -- advanced
```

Useful patterns:

```
\bword\b → exact word\s+ → spaces[0-9] → digits
```

👉 Learn basics, not full regex engine

---

### 🟡 3. Replace / Clean Text

```
REPLACE()REGEXP_REPLACE()
```

👉 useful for counting / cleaning

---

### 🟢 4. Length Tricks (Important)

```
LENGTH()
```

Used for:


count occurrences using difference 
```  rank() over(partition by user_id,action   
    ORDER BY   
      CASE WHEN action = 'page_exit' THEN timestamp END ASC,  
      CASE WHEN action = 'page_load' THEN timestamp END DESC  
      ) as rnk  ```
where action in ['page_load', 'page_exit']
```

👉 Square brackets `[]` are **not valid** in SQL for `IN`

---

## Correct Syntax

```
WHERE action IN ('page_load', 'page_exit') 
```  

redo this question [https://platform.stratascratch.com/coding/10352-users-by-avg-session-time/](https://platform.stratascratch.com/coding/10352-users-by-avg-session-time/ "https://platform.stratascratch.com/coding/10352-users-by-avg-session-time/")   count(case when action = 'sent' then 1 end) as sent, ... with group by it can be done  inside count we can use case