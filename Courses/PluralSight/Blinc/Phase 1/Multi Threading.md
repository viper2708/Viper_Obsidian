## Understanding Concurrency, Threading and Synchronization

* What is a Thread
    * A thread is defined at the Operating System level
    * A thread is a set of instructions
    * An application can be composed of several threads
    * Different threads can be executed "at the same time"
    * The Java Virtual Machine works with several threads (GC, JIT, etc)
* Who is responsible for the CPU sharing
    * A special element called a scheduler
    * There are three reasons for the scheduler to pause a thread
        * The CPU should be shared equally among threads
        * The thread is waiting for some more data
        * The thread is waiting for another thread to do something
* Race condition
    * It means that two different threads are trying to read and write the same variable at the same time
* Synchronization
    * Prevents a block of code to be executed by more than one thread at the same time
    * Locks are reentrant
        * When a thread holds a lock, it can enter a block synchronized on the lock it is holding
    * Deadlock
        * A deadlock is a situation where a thread T1 holds a key needed by a thread T2, and T2 holds the key needed by T1
        * The JVM is able to detect deadlock situations, and can log information to help debug the application
* Runnable interface
    * The most basic way to create threads is Java is to use the Runnable pattern
    * First create an instance of Runnable
    * Then pass it to the constructor of the Thread class
    * Then call the start() method of this thread object

## Implementing the Producer/Consumer pattern using Wait/Notify

* Stopping a thread
    * The call to interrupt() causes the isInterrupted() method to return true
    * If the thread is blocked, or waiting, then the corresponding method will throw an InterruptedException
    * The wait()/notify(), join() throw InterruptedException
* Producer/ Consumer
    * A producer produces values in a buffer
    * A consumer consumes the values from this buffer
    * Be careful : the buffer can be empty, or full
    * Producers and consumers are run in their own thread
    * Fixing the producer/ consumer
        * We need a way to "park" a thread while he is waiting for some data to be produced
        * Without blocking all the other threads
        * So the key held by this thread should be released while this thread is "parked"
        * This is the wait/notify pattern
* wait()/notify()
    * wait() and notify() are two methods from the Object class
    * They are invoked an a given object
    * The thread executing the invocation should hold the key of that object
    * wait() and notify() cannot be invoked outside a synchronized block
    * Calling wait()
        * Calling wait() releases the key held by this thread
        * And puts that thread in a WAIT thread
        * The only way to release a thread from a WAIT state is to notify it
    * Calling notify()
        * Calling notify() releases a Thread in WAIT state and puts it in RUNNABLE state
        * This is the only way to release a waiting thread
        * The released thread is chosen randomly
        * There is also a notifyAll() method
* A thread has a state
    * The thread scheduler can run the threads in the state RUNNABLE
    * A BLOCKED thread can only run again when the key is released
    * A WAITING thread can only run again when the notify() method is called

## Ordering Read and Write Operations on a MultiCore CPU

* Synchronization
    * Synchronization protects a block of code
    * Guarantees this code is executed by one thread at a time
    * Prevents race condition
* Memory Access
    * A CPU does not read a variable from the main memory, but from a cache
    * Because access to caches is much faster than access to main memory
        * Access to the main memory : 100ns
        * Access to the L2 cache : 7ns
        * Access to the L1 cache : 0.5ns
    * Tradeoffs
        * Size of the main memory : several GB
        * Size of the L2 cahce : 256kB
        * Size of the L1 cache : 32kB
* Visibility
    * A variable is said visible if the writes made on it are visible
    * All the synchronized writes are visible
* Happens before link
    * A "Happens before" link exists between all synchronized or volatile write operations and all synchronized or volatile read operations that follow
* What is "False Sharing"
    * False sharing happens because of the way the CPU caches works
    * It is a side effect, that can have a tremendous effect on performance