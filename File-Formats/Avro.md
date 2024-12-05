**How it stores data**  

- Its a row store file format
- Avro stores data in JSON format

- An Avro file is made up of a Header and Blocks of data
- Header contains file metadata, schema and codec details in addition to a 16-byte sync marker
- Each block contains  
    - Count of objects in the block
    -  size of serialized objects in the block
    -  Serialized object compressed by a codec
    -  16 byte sync marker

<img width="812" alt="image" src="https://github.com/user-attachments/assets/d291b98d-9137-433c-9b60-2b0b46805809">


**Advantages**  

- It is language neutral so can be used by multiple systems for data serialization
- It supports schema evolution quite well
- Provides rich data structures like array, enum etc.

