# Concurrency and Synchronization Project

This project demonstrates the principles of concurrency and synchronization in Java, focusing on multiple threads accessing a critical region.

## Explanation of Synchronization Choices

### Question 1: Choice between Synchronized Methods and Synchronized Statements

In this project, the choice was made to utilize synchronized statements for synchronization rather than synchronized methods. Synchronized statements allow for the protection of the critical region itself, ensuring that multiple threads do not interfere with each other's access to shared resources. Using the "synchronized" keyword in method headers would synchronize the entire method, applying the lock on the instance of the class. However, this approach wouldn't effectively prevent concurrent execution of the method by different instances. Therefore, synchronized statements were applied directly on the critical region (e.g., the reference of the `Account` object held in the `Accounts` array) by binding a lock to it, ensuring proper synchronization.

