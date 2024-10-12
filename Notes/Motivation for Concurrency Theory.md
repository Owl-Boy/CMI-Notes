---
tags:
  - Note
---
202408092008

Tags : [[Concurrent Programming]]
# Motivation for Concurrency Theory
---
## The Counter

A counter is a simple program that can be used as shared memory to demonstrate problems and solutions in concurrent programming. We will use the following *unsafe* implementation of a counter in some examples.

```java
class Counter {
    private long value;
    
    public Counter(long c) { // Constructor
        value = c;
    }

    public long get_and_increment() {
        long temp = self.value; // Start of danger zone
        self.value += 1;        // End of danger zone
        return temp;
    }
}

```

## Problems with Concurrency
Consider the following scenario:
- We want to go over a large range of numbers, and we have multiple threads available.
- To optimise for time, each time a thread is empty, we assign it a new number and let it process it.
- Once the processing is over, the thread becomes free again.
- Each time a thread wants a new number it uses the `get_and_increment` function of the counter.

The following is a possible issue:
- Thread 1 calls the function, the value 0 is stored in the current variable 'val'.
- before the counter can be updated, the second thread also calls the function and the value 0 is also stored in the variable 'val' for this thread. 
- After the functions are completely evaluated, both the threads get 0 as their number and the counter is updated to 2, this means that number 1 is not processed.

Hence methods like [[Mutual Exclusion]] need to be constructed to safely execute concurrent programs.

---
# References
