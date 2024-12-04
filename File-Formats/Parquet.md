**How it stores Data**  
- Parquet is a columnar data format which stores data in rowgroups  
- It stores data in files which have header, footer and Rowgroups.
- Header contains stats like min/ max values. It allows to skip reading blocks of data
- Footer contain schema details, format version, column metadata etc.
- Each Rowgroup contains multiple rows of data for all the columns in collocated chunks (ie. columnar storage) along with Column metadata. These chunks are guaranteed to be contiguous in file  
- Column chunks store a chunk of data for a particular column. 

<img width="573" alt="image" src="https://github.com/user-attachments/assets/92495474-141f-454e-a3b3-f719033d84fb">

  
**Advantages**  

- Very good compression -> results in fast read speeds
- Columnar storage -> fast reads as customer only reads the column needed in the query
- Language agnostic
- Open source - no vendor lockin
- Support for nested and complex data types better than ORC/ Avro


