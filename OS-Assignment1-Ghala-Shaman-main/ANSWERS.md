# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
A process is an independent program execution unit that has its own dedicated memory space and resources provided by the operating system.
 In contrast a thread is a smaller unit of execution that lives within a process and shares the same memory and resources with other threads in that process. 
 In this assignment 
 we used threads because they are "lightweight," meaning they have less overhead for creation and context switching compared to processes. 
Using threads allowed our simulation to easily share data structures, like the Ready Queue and process maps, without needing complex Inter-Process Communication (IPC) mechanisms

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**
In Round-Robin scheduling, if a process does not finish during its time quantum, it is placed back into the ready queue. This allows other processes to get CPU time before the unfinished process continues.
 In the simulation output, some processes complete only part of their execution during a quantum and then return to the ready queue.
 This behavior ensures fairness because all processes get a chance to execute. Without this mechanism, one process might monopolize the CPU and delay others.


[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
ظû╢ P3 executing quantum [4000ms]
  ظأة Quantum progress: [ظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûê] 100%
  ظ╕ P3 completed quantum 4000ms ظ¤é Overall progress: [ظûêظûêظûêظûêظûêظûêظûêظûêظûêظûّظûّظûّظûّظûّظûّظûّظûّظûّظûّظûّ] 47%
     Remaining time: 4462ms
  ظ╗ P3 yields CPU for context switch

  ظئـ P3(priority:2) added to ready queue ظ¤é Burst time: 8462ms
```
[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:**
[Explain what's happening in the output snippet you pasted]
my answer:

In this example, process P3 had a total Burst Time of 8462ms, which is longer than the Time Quantum of 4000ms. After executing for the full 4000ms, the process had 4462ms remaining. Therefore, the scheduler triggered a context switch, preempted P3, and moved it back to the end of the Ready Queue to allow other processes to run. This demonstrates the Round-Robin fairness principle where no single process can monopolize the CPU.


---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**


[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: [When is P1 in New state?]
P1 is in this state when the Thread object is first created in the code but before the start() method is called

2. **Runnable**: [When does P1 become Runnable?]
After start() is invoked, P1 enters the Ready Queue, waiting for the scheduler to grant it CPU time.

3. **Running**: [When is P1 Running?]
 P1 enters this state when the scheduler selects it and the thread begins executing its Burst Time logic.

4. **Waiting**: [When/why would P1 be Waiting?]
P1 may enter a waiting or timed-waiting state when it is put to sleep (via Thread.sleep()) or when it is re-queued after its time quantum expires.

5. **Terminated**: [When is P1 Terminated?]
Once P1 completes its total required Burst Time, it exits the loop and reaches the Terminated state, finishing its lifecycle.

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Name of application/scenario]

**Description**: 
[Describe the real-world scenario or application]

When a web server receives multiple simultaneous requests from different users to load a website.
**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]

 It allows the server to handle multiple connections "at once" by giving each request a small slice of processing time. This prevents a large file download from blocking other users who are just trying to load a small text page, improving the overall responsiveness for all users.


### Example 2: [Name of application/scenario]

**Description**: 
[Describe the real-world scenario or application]

When a user runs multiple applications simultaneously, such as a web browser, a music player, and a code editor.



**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]
 The OS uses Round-Robin to switch between these applications so rapidly that the user perceives them as running at the same time. It provides a smooth user experience by ensuring that no single application freezes the entire system while performing a task.
---

## Summary

**Key concepts I understood through these questions:**
1. The efficiency of using threads for resource sharing within a single application
2. How the Time Quantum regulates CPU fairness in a multi-threaded environment.
3. The specific triggers that move a thread between different states in the Java Virtual Machine (JVM).

Concepts I need to study more:

**Concepts I need to study more:**
1.threads  
2. practice coding more
