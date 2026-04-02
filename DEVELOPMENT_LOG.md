# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 20, 2026, 7:30 AM]
**What I did**:
Set up the project and ran the initial code
**Details**: 
Opened the project in VS code
Added my student ID (445052295) in the required line
Compiled and ran the program successfully
Observed the initial scheduler output to understand how it works
**Challenges**: 
The program didn’t run at first because of environment setup issues
**Solution**: 
Fixed the setup in VS code and ensured Java was properly configured
**Time spent**: 

---

### Entry 2 - [March 21, 2026, 9:00 AM]
**What I did**: 
Added priority to processes
**Details**: 
Added a priority field (1–5) to each process
Generated random priorities
Modified the process creation to include priority
Updated the output to display priority when adding to the queue
**Challenges**: 
Didn’t know how to sort the queue based on priority while still using threads
**Solution**: 
Used a PriorityQueue and a comparator
Connected threads to processes using a HashMap to access priority
**Time spent**: 
3 hours
---

### Entry 3 - [March 22, 2026, 6:30 PM]
**What I did**: 
Fixed scheduling behavior
**Details**: 
Made sure processes are re-added correctly after each quantum
Tested multiple runs to check if higher priority processes are executed first
Verified that unfinished processes go back to the queue properly
**Challenges**: 
At first, the execution order didn’t always follow priority correctly
**Solution**: 
Fixed the comparator logic and ensured the queue updates after every execution
**Time spent**: 
2 hours
---

### Entry 4 - [March 23, 2026, 5:00 PM] Time]
**What I did**: 
Implemented waiting time calculation
**Details**: 
Added variables to track waiting time for each process
Calculated waiting time before each execution
Accumulated total waiting time across multiple cycles
**Challenges**: 
Waiting time values were incorrect at the beginning 
**Solution**: 
Fixed the timing by updating enqueue time correctly after each run
**Time spent**: 
2 hours 30 minutes
---

### Entry 5 - [March 24, 2026, 10:00 AM]
**What I did**: 
Improved output and added extra features
**Details**: 
Displayed the ready queue before each process runs
Added context switch counter
Implemented "run to completion" for the last process
Created a summary table for all processes
**Challenges**: 
Formatting the output nicely without breaking alignment
**Solution**: 
Used String.format and adjusted spacing through trial and error 
**Time spent**: 
3 hours
---

### Entry 6 - [March 26, 2026, 8:00 AM]
**What I did**: 
Final testing and verification
**Details**: 
Ran the simulation several times to verify correctness
Checked that priority scheduling works properly
Verified waiting time and context switches
**Challenges**: 
Making sure everything works together correctly (priority + round robin)
**Solution**: 
Carefully reviewed the output step by step 
**Time spent**: 
1 hour
---

## Summary

**Total time spent on assignment**: [8-9 hours]

**Most challenging part**: 
The hardest part was getting the scheduling behavior correct when combining priority with round robin. At the beginning, the order of execution wasn’t always right, and it took some time to understand how the PriorityQueue and threads interact together.
**Most interesting learning**: 
Understanding how CPU scheduling actually works in practice, especially how processes move in and out of the ready queue. Also learned how small changes (like comparator logic) can completely affect scheduling behavior.
**What I would do differently next time**: 
 I would plan the structure earlier instead of modifying things step by step, because some parts (like priority and waiting time) had to be adjusted multiple times.
