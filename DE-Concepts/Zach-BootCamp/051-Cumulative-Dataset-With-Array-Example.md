- Cumulative datasets are used to maintain history data while processing current data. E.g. building DIM_Users table for facebook would need to keep and manage history of users. Yesterday data is cumulated history which needs to be merged with today's data
  

- Cumulative datasets are a nice way to store aggregate data which can be used for rollups and further layers of aggregations, without having to scan the detailed data again and again.   

- The way we store cumulative data allows us to read the relevant data and aggs without having to shuffle the data or reading multiple records

**Example**  

For the Uber Eats problem where we need hourly/ daily/ weekly aggregated data to be reported, hourly Aggregations will happen in the Spark/ Flink layer. The moving hourly data to be stored can be something like this (the example is for one KPI, same can be implemented for all three KPIs):  

<img width="453" alt="image" src="https://github.com/user-attachments/assets/acbcab5e-7b5a-4a5d-90e8-6014ac6e44bf" />


We can leverage cumulative datasets to convert this same dataset to be used for larger aggregations. With the following design, we don't need to re-compute the aggregates. Also, with this design, we don't need to shuffle data for larger aggregations, we can just read one row (for a restaurant id) and the single row will contain all the information. This example is for all hours of a day, we can run an agg pipeline to build daily/ weekly/ monthly dataset on top of this dataset as well, with a similar design :  

<img width="500" alt="image" src="https://github.com/user-attachments/assets/d99201c3-5713-4141-a6a9-f616b80f9015" />
