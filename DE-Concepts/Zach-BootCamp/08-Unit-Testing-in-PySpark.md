This doc outlines a way to do unit testing in PySpark and how to do Test Driven Development for Spark based DE work.  

The approach is like this:  
- For every transformation, wrap it in a function (F1) so that it can be tested in unit tests. PyTest and Chispa libs are used here to test functions for expected output  
- create a new test file in the test folder
- Every function (F2) we want to be evaluated in the test file should start with TEST, else PyTest will not pick it up
- In the test function (F2), we define the source data and expected data. We also run the source data through the actual function (F1) that needs to be tested to generate OutputData
- We execute an Assert between ExpectedData and OutPutData

**Example**  
This is a test file which is trying to test the function "do_team_vertex_transformation"    
 input_data is being provided  
 expected_output is being provided  
 input data is run through the function do_team_vertex_transformation to generate actual_df  
 actual_df and expected_df are run through an assert to check for equality


<img width="1395" alt="image" src="https://github.com/user-attachments/assets/a31f39ee-1cd6-4cee-82cf-8a958f0d8e5f" />  

This is what the project structure looks like:  

<img width="806" alt="image" src="https://github.com/user-attachments/assets/890a9e7a-9d73-4d8d-a07d-e759e822203e" />

