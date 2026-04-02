# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

I learned how multithreading allows multiple tasks to run concurrently, improving CPU utilization. In this assignment, I used threads to simulate processes where each process runs for a specific time quantum. I understood how start() initiates execution and join() forces the main thread to wait for completion, which was crucial for Round Robin scheduling. I also learned that threads share memory, so careful management of shared data structures like the ready queue is necessary. Overall, this assignment connected theoretical scheduling concepts to practical multithreading implementation.

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

The most challenging part was implementing priority scheduling combined with Round Robin correctly. Ensuring higher priority processes execute first required careful implementation of the PriorityQueue comparator, but I encountered a NullPointerException when the comparator was called with null values. Another challenge was tracking waiting time accurately across multiple quantum executions. The formatting error in the summary table (IllegalFormatConversionException) was also tricky because mixing colored strings with numeric format specifiers caused crashes. These challenges tested my understanding of both scheduling algorithms and Java implementation.
---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

I overcame challenges using systematic debugging and incremental testing. I added temporary print statements to track process states, priority values, and queue contents. I tested incrementally, starting with 2 processes then increasing to 16, which made bugs easier to isolate. For the NullPointerException, I added null checks in the comparator and moved processMap declaration before the queue. For the formatting error, I changed %d to %s after reviewing Java's String.format() documentation. This methodical approach helped me fix all issues and achieve correct scheduling behavior.
---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**

Multithreading is essential in many real-world applications. E-commerce platforms like Amazon use threads to process multiple customer orders simultaneously, especially during sales events. Ride-sharing apps such as Uber use threads to track driver locations, match riders, and process payments all at the same time. Social media platforms like Instagram use threads to handle uploading photos, loading comments, refreshing feeds, and sending notifications concurrently. Banking systems use threads to process multiple ATM transactions and online transfers without interfering with each other. Artificial intelligence applications use threads to run multiple model training tasks in parallel, significantly reducing training time. This assignment helped me understand how modern software stays responsive and efficient even when doing many things at once.
---

## Additional Reflections (Optional)

### What would you like to learn more about?

[Any topics related to threading, concurrency, or operating systems that you're curious about?]

---

### How confident do you feel about multithreading concepts now?

[Rate yourself and explain: Beginner / Intermediate / Confident]

[Explain your rating - what do you understand well? What needs more practice?]

---

### Feedback on the assignment

[Any comments about the assignment? Was it helpful? Too easy/hard? Suggestions for improvement?]
