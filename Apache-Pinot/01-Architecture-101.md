- Apache Pinot uses tightly coupled storage and pre-allocated compute to minimize query latency.
  
  - Imagine a CPU and local disk storing data collocated and most of the query processing happening there itself over a very high bandwidth network connection. The storage is mostly local SSD, making it very fast to access data from the disk.
  
  - This is in contradiction to a lot of other MPP systems which rely on compute and storage segregation.
      
