.   This is a simple Database Management System developed using Java . The following files were completed during the course:-

Anumeha :-

1) TupleDesc :- I used an ArrayList to store the TDItems . I initially had some problems with the boolean method but later used explicit conversions and 
fixed the error.

2) BufferPool - The bufferpool was relatively simple but I faced some issues with iterator which was fixed by creating a dynamic array with the tableIds and iterating through 
that.
3) Catalog - I used HashMap to implement this class which made it easier to implement getPage method.

4) Integer Aggregator - I used HashMap in the case where gfield is not null and ArrayList where gfield is null. I created a private method called aggfunctions to perform COUNT, ADD , MAX, MIN & AVG. I faced some problem in the iterator method but after referring to DBIterator and TupleIterator I was able to solve this. This file took quite some time though.

5. String Aggregator - This file was easy to code as it was very similar to Integer Aggregator

6) Aggregate :- The Aggregation operator computes an aggregate. This class mostly contained methods which returned various fields needed for the 
String and Integer Aggregator. I faced some problems in the open method but I referred to the Operator file and found out that I had to use 
the call the function using super to use the methods in operator.
