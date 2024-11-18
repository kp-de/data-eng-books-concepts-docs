**What are Idempotent Pipelines?**   

Idempotent Pipelines should produce the same result:  
- Regardless of the day you run it
- Regardless of how many times you run it
- Regardless of the hour that you run it


**Tips to make a pipeline idempotent**  
- Use Merge or Insert Overwrite (instead of insert into)
- Always use both Start_Date > and End_Date < conditions (only one will be a problem)
- If you have a cumulative pipeline (where today can only run after yesterday), then dependency management should be done accordingly. In Airflow, use the "depends on past" param
- If you are using an SCD table, always make sure you are using proper flags to identify the "as of date" current record from SCD table

  
