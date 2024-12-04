**There are three basic ways to minimize the amount of data is being read/ processed**  

- Only read the columns you need : Use Columnar Databases/ file formats. e.g. Parquet and ORC are columnar formats

- Minimize the amount of data being read: Use Compression. Run Length Encoding is one of the best which works for fields having repeated values

- Limit the number of rows you are reading: Use Partitioning.

**Partitioning**  

- Mostly on date fields and then on a low cardinality field with few distinct values  
- E.g. For Facebook notifications, first partition on date and tehn on Channel which has very few unique values like Mobile, Web, Tablet etc.
