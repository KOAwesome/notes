Topic:

Context:

Error / Observation:

Root Cause:

Fix Applied:
```java
int[] example1 = list.stream().mapToInt(i->i).toArray();
// OR
int[] example2 = list.stream().mapToInt(Integer::intValue).toArray();
```

Verification:

Prevention / Rule:

Code Snippet (optional):

References:
