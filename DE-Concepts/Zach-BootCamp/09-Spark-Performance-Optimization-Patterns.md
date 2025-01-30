1. Shuffle joins won't work after the datasets grow beyond few hundred TBs. What to do in these scenarios?


Use bucketed joins:  
Bucket both tables   
Use the buckets for joins without shuffles  
Even if the number of buckets are not same for both tables, if number of buckets can be multiple of one another, it works fine  
Be careful because Bucketing will also incur shuffling. So, you will only benefit when you are doing multiple joins (to offset the one time shuffle cost)  

![image](https://github.com/user-attachments/assets/e3180689-2112-4cfe-9dff-0188a67e8875)  


Another left field solution can be to solve the problem before Spark (and in the application layer itself) to avoid the join requirement itself.
Example, when joining Network Ips to Microservices in the app can be done at the join level if these are in two different tables. But, if you can talk to the app team to include the Microservice name in the logs with the Ips, then you don't need to join the two datasets to get the same information.
 

2. Skew problem


Another way to solve the skew problem is to separate out the skewed value into another pipeline. That way, your other partitions run like usual while your bigger partitions can be taken care of in a separate pipeline  

![image](https://github.com/user-attachments/assets/ccbba028-925f-4554-9de6-4fe36ac5dacc)  



3. Df.sortwithinPartitions() only sorts within each partition while DF.sort() does a global sort across partitions. DF.sort() is very slow at scale as it forces shuffle (exchange rangepartitioning will happen if you see the explain plan). Only use the .sort() when you truly need a global sort on your dataset

Use sorting with Run Length Encoding to reduce the size of datasets. For big datasets, this can be substantial savings in read time and storage costs  

4. Caching CTEs/ Temp Views:

<img width="1255" alt="image" src="https://github.com/user-attachments/assets/0353fe26-c38c-4c53-b462-2293ed45ad29" />    



5. Caching vs Broadcast Joins: Caching can be used for bigger datasets as it still partitions data


<img width="1255" alt="image" src="https://github.com/user-attachments/assets/266b8b76-1a84-498c-9729-ee2de696bb8d" />


