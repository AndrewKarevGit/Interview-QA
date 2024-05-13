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
