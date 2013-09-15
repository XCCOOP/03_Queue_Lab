03_Queue_Lab
============

Implement an array-based queue in C++

Note: When you create your project, do NOT add ArrayQueue.ipp to the list of source files, add it to the list of include files. You will see that ArrayQueue.ipp is #included at the bottom of ArrayQueue.h. See ArrayQueue.h for more explanation.

Requirements
------------

1. remove takes O(1) time
2. add takes O(1) time, unless it calls grow (in that case O(n) is okay)
3. grow is only called if the number of items == backingArraySize, and the size of the array is doubled during grow
4. grow takes O(n) time
5. Do not leak memory (make sure grow and the destructor do the right thing)
6. getNumItems is O(1) time
7. add and remove throw excpetions as appropriate
8. You must use the array in a circular fashion. If you don't do this you probably won't be able to get #1, #2 and #3 to all be true.

Reading
=======
"Open Data Structures," Chapter 2, up through section 2.4 (ArrayDequeue). http://opendatastructures.org/ods-cpp/2_Array_Based_Lists.html

Questions
=========

#### 1. Which of the above requirements work, and which do not? For each requirement, write a brief response.

1. TODO
2. TODO
3. TODO
4. TODO
5. TODO
6. TODO
7. TODO
8. TODO

#### 2. If we did a Stack instead of a Queue, which of the private methods and variables would we need to keep, and which could we get rid of? Explain your answer.

The methods to keep:

get()

set()

add()

resize()

remove()

//*************************************************************


The variables to keep:

The number of element.


The variable to get rid of:

The integer to store the first index of element in the queue.


//*************************************************************


Why keep them?

The get(), set(), and add() methods are definitely necessary, performing to

get elements, set elements, and add elements from stack and queue. Resize()

method is to increase the size of stack and queue when they are full. Remove()

method is to delete elements from stack and queue.


//***********************************************************


Why kick them?

Because stack is last in first out policy, so keep the index of first element

in the stack is useless. But you might ask why don't we just keep it and do a

circular-stack like we use this variable to do a circular-queue? The answer is 

because stack is LIFO policy like I said before, you can image that you are

stacking plates, there is no way to go back to previous index.








#### 3. What is one question that confused you about this excercise, or one piece of advice you would share with students next semester?


Implementing Queue by using circular-array based is very useful.



#### 4. In Java you might write "class ArrayQueue extends Queue" ... how do you write the same thing in C++?

class ArrayQueue :: public Queue {};


#### 5. What is the purpose of "templates" in C++?

1. To avoid repeating code which is identical except for different types.

2. To generate code in compile time.



#### 6. What would the syntax be for dynamically allocating an array of 10 ints, in C++?
 
 //Allocate the memory.

 int *array = new int[10];
 
 //Free the memory

 delete [] array;

 //Even though you free the memory, but it is still pointing somewhere, isn't it
 ?
 array = NULL;


#### 7. What is the purpose of a class destructor in C++? Why don't you need them in Java?

Java uses managed memory, programmers can allocate memory by using new operator,
and deallocate memory by relying on the garbage collector. Java takes care of
memory management for programmers. However, C++ doesn't handle its own memory, 
every time the programmers use delete() method the destructor of given 
arguement will be called, and return memory allocated by new back to heap in
order to avoid memory leak.







