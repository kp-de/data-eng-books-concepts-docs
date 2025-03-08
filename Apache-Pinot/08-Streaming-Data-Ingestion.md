**Streaming data ingestion or Real Time Tables Ingestion**  

- Pinot table acts as a consumer of a Kafka topic  
- Incoming data from Kafka gets written in an in-memory data structure "Consuming segment".
- This segment can be on any one of the servers for this table. Controller will assign this job to any server, and then the server will create a Kafka consumer
- Consumed data is available for querying as soon as it gets written in the "Consuming Segment"
- Consuming segment fills up and then we need to flush it to a Segment on disk. Flushing can be based on Memory Threshold, Number of records, time etc.
- Flush of different segments will get distributed to different servers. Over time, even the Kafka consumer can get created on a different server    
  


<img width="1040" alt="image" src="https://github.com/user-attachments/assets/f7540601-d218-417d-a906-087b31b2ad39" />   

<img width="1040" alt="image" src="https://github.com/user-attachments/assets/fac1e091-c21d-4fc3-a70f-794622a6891f" />  

<img width="1241" alt="image" src="https://github.com/user-attachments/assets/e5c8030f-174a-45d4-9de1-0a316b41cab4" />



