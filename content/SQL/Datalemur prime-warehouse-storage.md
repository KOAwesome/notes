![[Pasted image 20251228092955.png]]
https://datalemur.com/questions/prime-warehouse-storage 
FLOOR (500000/total_sqft)
500,000/555.2 = 900.5763688761= 900
That many batches possible.. 
	so total sqft = 900 *555.2=4,99,680
	so some small part is left 320
	1 batch = 6 items
	so 900 batches = 5400
for non prime similarly 320/128.40 =2.492211838  = 2 batches
1 batch = 4 items
so 2 batches = 8 items



```
prime AS (
SELECT 
  item_type,
  FLOOR (500000/total_sqft) * total_sqft AS total_prime_area,
  FLOOR (500000/total_sqft) * total_count AS total_prime
FROM 
  cte
WHERE item_type = 'prime_eligible'
)
```
