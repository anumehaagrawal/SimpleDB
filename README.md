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


Praveen Raj :-

1. RecordId :- This was a fairly easy class, but I faced a problem with the implementation of hashCode method. Later I figured it out after looing at the return type and taking cues from other classes too.

2. HeapPageId :- Here I built a constructor using global variable. Here too I had a problem with hashCode. Initially I had implemented it using string concatenation and returning the interger obtaibed by parsing the string. But that gave error because its format was not suitable for the HashMap. So later I implemented it using bitwise operator, in which I just concatenated the integers in a specific way.

3. HeapPage :- HeapPage implemented Page interface. This was a fairly difficult class for me. The major problem I faced was with the implementation of isSlotEmpty method. After spending a lot of time I implemented it using bitwise operation, which I came up with after looking at the structure of the header. And I used almost similar logic to implement markSlotEmpty method. In here, I used the ArrayList in the iterator method which helped me as I could use the in built ArrayList.iterator method for my purpose.

4. HeapFile :- Here inorder to implement the iterator I created a new class HeapFileIterator which implemented DbIterator. Its structure is mostly influenced by TupleIterator and for its implementation, I have also referred the HeapFileTest. In the insertTuple method I used ArrayList for storing and also for adding pages.
