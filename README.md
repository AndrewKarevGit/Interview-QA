# Interview QA
#### Here is a list of interview questions that I analyzed and the answers to them

## 1. List the methods of the Object class
- final Class<?> getClass()
- int hashCode()
- boolean equals(Object obj)
- Object clone() throws CloneNotSupportedException
- String toString()
- final void notify()
- final void notifyAll()
- final void wait(long timeout) throws InterruptedException
- final void wait(long timeout, int nanos) throws InterruptedException
- final void wait() throws InterruptedException
- void finalize() throws Throwable


## 2. Why are equals & hashCode methods needed?
For value objects, we usually prefer equality based on their properties.
It's why we're override equals() and also hashCode(), to avoid the mistakes 
in collections


## 3. What happens if you override equals but not override hashCode?
Example: If only equals is overriden, then when you call myMap.put(first,someValue)
first will hash to some bucket and when you call myMap.put(second,someOtherValue)
it will hash to some other bucket (as they have a different hashCode).
So, although they are equal, as they don't hash to the same bucket,
the map can't realize it and both of them stay in the map.

## 4. Why do we need the wait, notify, notifyAll methods?
The wait(), notify(), and notifyAll() methods are used for signaling
and communication between threads. Threads can wait for a condition
to become true using wait(), and other threads can notify or signal
when that condition is met using notify() or notifyAll().

## 5. How to clone an object correctly?
- a) Implement Clonable interface
- b) Override clone() method

## 6. Why is the Finalize() method needed and how does it work?
The finalize() method in Java is a method of the Object class used to perform
cleanup activity before destroying any object. Garbage collector calls it
before destroying the objects from memory. finalize method in Java is called
by default for every object before its deletion.

## 7. What is the difference between final, finally, finalize?
Final is a keyword used in Java to restrict the modification of a variable, method,
or class. finally is a block used in Java to ensure that a section of code is always
executed, even if an exception is thrown. finalize is a method in Java used to perform
cleanup processing on an object before it is garbage collected.

## 8. What are try-with-resources?
The try-with-resources statement is a try statement that declares one or more resources.
A resource is as an object that must be closed after the program is finished with it.
The try-with-resources statement ensures that each resource is closed at the end
of the statement.

## 9. What is the difference between the wait(1000) and sleep(1000) methods?
The code sleep(1000); puts thread aside for exactly one second. The code wait(1000),
causes a wait of up to one second. A thread could stop waiting earlier if it receives
the notify() or notifyAll() call. The method wait() is defined in the class Object and
the method sleep() is defined in the class Thread.

## 10. What is the difference between i++ and ++i?
++i will increment the value of i , and then return the incremented value. i++ will
increment the value of i , but return the original value that i held before
being incremented.

## 11. How to properly compare two strings in Java?
To compare strings in Java for equality, you should use String. equals() .
If uppercase and lowercase difference isn't important, you can use String. equalsIgnoreCase()

## 12. How to sort a list of strings alphabetically?
For example, if you have a list of strings and you want to sort them in alphabetical order,
you can use the List. sort() method. List. sort() is an instance method of the List class
and it sorts the elements in the order defined by their natural ordering or by a specified
Icomparer implementation.

## 13. What encoding are strings stored in in Java?
String objects in Java are encoded in UTF-16

## 14.
```
String s = "Java";
byte[] buffer = s.getBytes("Windows-1251");
```
