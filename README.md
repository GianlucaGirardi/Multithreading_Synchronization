# Concurrency and Synchronization Project

This project demonstrates the principles of concurrency and synchronization in Java, focusing on multiple threads accessing a critical region.

## Project questions and answers

### Question 1: Choice between Synchronized Methods and Synchronized Statements

In this project, the choice was made to utilize synchronized statements for synchronization rather than synchronized methods. Synchronized statements allow for the protection of the critical region itself, ensuring that multiple threads do not interfere with each other's access to shared resources. Using the "synchronized" keyword in method headers would synchronize the entire method, applying the lock on the instance of the class. However, this approach wouldn't effectively prevent concurrent execution of the method by different instances. Therefore, synchronized statements were applied directly on the critical region (e.g., the reference of the `Accounts` object held in the `Accounts[]` array) by binding a lock to it, ensuring proper synchronization.

### Question 2: Choice between Busy-waiting and Semaphores

Implementing semaphores using the `acquire()` and `release()` methods yields faster execution times compared to busy-waiting. Busy-waiting, characterized by continuous looping until a condition is met, significantly boosts CPU usage, leading to inefficient resource utilization. Conversely, the `acquire()` method behaves differently. When conditions are not met, the thread enters a waiting state, halting its execution until the conditions are satisfied, unlike the continuous looping in busy-waiting implementations. This method optimally utilizes CPU resources, avoiding the constant polling inherent in busy-waiting. Additionally, it minimizes the number of context switches, further enhancing performance. When calling `acquire()`, the thread enters the waiting state and lives out the rest of its scheduled time before undergoing a context switch. What makes this approach advantageous is that the thread cannot be picked up by the CPU until its conditions are met, ensuring efficient waiting and reducing unnecessary CPU usage.
