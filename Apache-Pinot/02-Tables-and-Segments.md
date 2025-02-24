<img width="983" alt="image" src="https://github.com/user-attachments/assets/66c8a1ef-7ade-4bab-b20f-d0f3518a5093" />  

**Offline Tables**  
Live, available table which contains batch data - no real time ingestion is happening in these tables  

**Real time tables**  
Some stream is being ingested in this table in real time  

**Hybrid Tables**  
You might have files having data somewhere and with the same structure of tables, you might also be having stream data getting ingested in this table. Effectively, its a combination of both offline and rela-time tables  

<img width="1304" alt="image" src="https://github.com/user-attachments/assets/7c408cf8-7926-45b2-8f74-2a088d7ec0a1" />  

<img width="1301" alt="image" src="https://github.com/user-attachments/assets/40264e1d-69f6-4e91-aeb6-e871f6d403c1" />  

<img width="1301" alt="image" src="https://github.com/user-attachments/assets/261a7b73-1db1-42df-be24-ed83b81ea3d7" />   



Effectively, all the fields are stored contiguously on the disk but in a columnar format, that allows encoding and compression of individual fields based on type of values in a field.



