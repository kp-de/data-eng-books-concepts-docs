**How data is stored**  

- Data is stored in stripes. Each stripe is 250 MB  
- Each stripe has an index, footer and Raw data  
- Index has stats like min, max column level stats etc. which help in predicate pushdown
- Footer has schema details
- Row data has chunks of columnar data

<img width="445" alt="image" src="https://github.com/user-attachments/assets/48da5348-e05d-4d0b-a331-25a3b4405d46">


**Advantages**  
- Fast reads because of compression and columnar storage
- Bloom filters, predicate pushdown supported
- Schema evolution is supported for new column additions
- Works bests for Hive and Presto
