# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
A process has its own isolated memory space, while threads share memory within the same process, making communication faster. Creating processes has higher overhead because the OS must allocate separate resources, whereas threads are lightweight and efficient. We used threads in this assignment because multiple simulated processes need to share the same ready queue and process map. Threads also allow us to use join() to synchronize execution, which would be complex with separate processes. The Process class implements Runnable, and each simulated process runs as a thread created by new Thread(process).


---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

When a process doesn't finish within its time quantum, it is preempted and moved to the end of the ready queue. In my output, P1 had 6942ms burst time with 3000ms quantum, leaving 3942ms remaining, so it yielded CPU and was re-added to the queue.

Example from my output:
```
P1 yields CPU for context switch
P1 (Priority: 5) added to ready queue
```

**Explanation of example:**
This re-queueing is important for fairness because it prevents long processes from monopolizing the CPU. Without it, short processes like P9 (1574ms) would starve while P1 (6942ms) runs continuously. Round-Robin guarantees every process gets CPU time within a bounded waiting period.

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: [P1 enters the New state when its thread object is first created using new Thread(process) in the addProcessToQueue() method. At this point, the thread exists but has not yet started execution.
]

2. **Runnable**: [P1 enters the Runnable state when currentThread.start() is called after being polled from the ready queue. The thread is now ready to run and waiting for CPU scheduling.]

3. **Running**: [P1 enters the Running state when the CPU actually begins executing its run() method. During this time, P1 runs for one time quantum (3000ms) and displays progress updates.]

4. **Waiting**: [P1 enters the Waiting state multiple times during its quantum when Thread.sleep(stepTime) is called to simulate progress. Each sleep lasts for a fraction of the quantum, allowing the progress bar to update.]

5. **Terminated**: [ P1 enters the Terminated state after its final quantum when remainingTime becomes 0. The run() method exits, and the thread completes its lifecycle permanently.]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Online Game Server (e.g., Among Us, Minecraft)]

**Description**: 
[An online game server manages multiple players moving, chatting, and performing actions simultaneously. Each player's device sends updates to the server, which must process all players fairly to keep the game smooth for everyone.
]

**Why Round-Robin works well here**: 
[Round-Robin ensures each player gets equal CPU time, preventing one player with a bad connection or fast clicking from slowing down others. If a player's actions take too long to process, the server pauses them and moves to the next player, similar to how my simulation's processQueue cycles through P1, P2, P3. This keeps the game responsive and fair for all players, just like my timeQuantum prevents any single process from hogging the CPU.
.]

### Example 2: [Print Queue in a Shared Office
]

**Description**: 
[in an office with 20 employees sharing one printer, multiple people send print jobs simultaneously. Some jobs are short (one page), while others are long (100 pages). The printer can only print one document at a time.
]

**Why Round-Robin works well here**: 
[Round-Robin allows the printer to print a few pages from each document in rotation instead of finishing one completely before starting the next. This prevents the person with a 100-page report from making everyone else wait an hour. Each document gets a "time quantum" of pages printed before switching to the next, similar to how my simulation re-queues unfinished processes. This feels fair to all employees because everyone sees their document making progress.
]

---

## Summary

**Key concepts I understood through these questions:**
1. Thread vs Process: Threads share memory making communication faster, which is why we used them in my scheduler.

2. Round-Robin Fairness: When a process doesn't finish its quantum, it goes to the back of the line, preventing any process from being skipped forever.

3.Thread Lifecycle: A thread moves through New → Runnable → Running → Waiting → Terminated states, controlled by methods like start(), join(), and sleep().
 

**Concepts I need to study more:**
1. Synchronization: How to safely share data between threads without causing conflicts.

2.  Deadlocks: What happens when two threads are both waiting for each other to finish? This can freeze a program, and I want to learn how to prevent it.

