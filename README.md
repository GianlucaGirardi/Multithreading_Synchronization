Project demonstrating concurrency and synchronization of multiple threads accessing a critical region.

Q1: Explain your choice of using either synchronized methods or synchronized statements. 
Answer: In this case, applying synchronization statements ensures the protection of the critical region itself rather than attempting to block two threads from executing the same method concurrently. 
This being said, using the "synchronized" keyword in the method header will not work as intended. In fact, the method will be synchronized on the instance of the class: the lock will be applied on the instance of the class and other threads calling the synchronized method on a different instances will not be blocked.
Therefore, synchronization statements can be applied on the critical region itself (the reference of the Account object being held in the Accounts array, ex: account[i]) by binding a lock to it.
