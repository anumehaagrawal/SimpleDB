# SimpleDB.  
This is a simple Database Management System developed using Java . The following files were completed during the course:-

#### Anumeha :-

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


#### Praveen Raj :-

1. RecordId :- This was a fairly easy class, but I faced a problem with the implementation of hashCode method. Later I figured it out after looing at the return type and taking cues from other classes too.

2. HeapPageId :- Here I built a constructor using global variable. Here too I had a problem with hashCode. Initially I had implemented it using string concatenation and returning the interger obtaibed by parsing the string. But that gave error because its format was not suitable for the HashMap. So later I implemented it using bitwise operator, in which I just concatenated the integers in a specific way.

3. HeapPage :- HeapPage implemented Page interface. This was a fairly difficult class for me. The major problem I faced was with the implementation of isSlotEmpty method. After spending a lot of time I implemented it using bitwise operation, which I came up with after looking at the structure of the header. And I used almost similar logic to implement markSlotEmpty method. In here, I used the ArrayList in the iterator method which helped me as I could use the in built ArrayList.iterator method for my purpose.

4. HeapFile :- Here inorder to implement the iterator I created a new class HeapFileIterator which implemented DbIterator. Its structure is mostly influenced by TupleIterator and for its implementation, I have also referred the HeapFileTest. In the insertTuple method I used ArrayList for storing and also for adding pages.

#### Nachiket :-

1. ```SeqScan``` :- Before implementing any of the methods I had to understand the role/relevance of other classes.  I used many methods from other classes like Catalog, Database, DbFile etc. Figuring out which methods(from other classes) to use while  implementing, was the part I struggled with.I didn't know much about iterators, so read about them a bit before writing the iteration part of SeqScan. Rest of the methods were relatively easy to complete.

2. ```HeapFile``` :- Few methods of HeapFile were easy to implement.Methods like  ```readPage()```,```writePage()``` were relatively a bit hard. The implementation guide stated to use Random Access(RAF) to read/write the files.I had to read about RAF in Java to implement the above methods.Fixed a few errors occured while using RAF. Also I had to refer to DbFile class to know more about the methods.

3. ```Insert``` :-To implement Insert Class I had to refer the Operator Iterator Class. There I learned about the super keyword used to refer the parent class. Methods were easy to implement. Got a few Exception errors, which were fixed by catching them.

4. ```Delete```:- Delete Class is very similar to Insert Class. Implementing it didn't take much time.

5. ```BufferPool``` :- Here I implemented the ```LRU``` eviction policy of BufferPool. I first thought of using an arraylist or an queue but then discarded them as updating/reshuffling an arraylist according to eviction priority would be rather difficult. I finally used a HashMap with PageId as key and the value referring to the key as priority parameter.

   Recently added page will have priority of value 0 and Least Recently Used Page will have highest priority value which will eventually be evicted. I modified the ```getPage()``` method to suit the eviction policy.I created a new method to ```updatePriority()``` to update the HashMap keyvalue. Implementing evict page was a bit tougher. I ran into Exception errors in Eviction System Test, but fixed them with try() and catch().
   
#### Shubham :-

1. Tuple :- It was a fairly easy class with very less coding to do.This is implemented with an array of Fields so as to have random access for setting and getting fields. The iterator is implemented by wrapping the array in a Java ArrayList and returning the iterator (had to look this up).

2. Filter :- This class was created to filter out the tuples according to the constructor in the class.The process of iteration and applying the predicate took some effort otherwise the rest of the code was similar to what we had done before.function here was fetchNext, which iterated through the child iterator, applying the predicate filter function to see do the selection.


3. Join :- This class implementation took a lot of time and i faced a lot of difficulties. i used a nested loop join. The join is done by iterating through the values of the column of the first join field and using the predicate to determine if it should join based on the join field on the right. If so, a new TupleDesc is made and the two corresponding tuples are merged.

4. Predicate :- This file only had some getter/setter methods and made use of Field's compare method

5. JoinPredicate :- This file was also very simple and made use of Field's compare functionThis file was also very simple and made use of Field's compare function.
ps: I faced problem mostly in the join and joinpredicate classes.

