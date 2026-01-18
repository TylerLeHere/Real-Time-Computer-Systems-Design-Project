# Week 1

- Release Time: It is the instant time when a job becomes available for execution. 
- Response Time: It is the length of time from the release time of 
the job to the time instant when it completes.
- Interrupt: It is a hardware signal that initiates an event to be process by the CPU.
- Completion Time: The exact instant when the job finishes its final instruction

# Week 2
### Hard vs. Soft Real-Time Systems

**Core Concept:** The "firmness" of the timing constraint affects how we reason about and engineer the system.

| System Category | Definition | Tolerance & Consequence |
| :--- | :--- | :--- |
| **Hard Real Time** | A job must **never** miss its deadline. | **Zero Tolerance.** <br> Missing a deadline is considered a total system failure (often catastrophic). The result is useless if late. |
| **Firm Real Time** | A **low probability** of violating a response-time is tolerable. | **Low Tolerance.** <br> The system can survive occasional misses, but the data is likely useless if late (value drops to zero). |
| **Soft Real Time** | Some deadlines can be **missed occasionally**. | **High Tolerance.** <br> The system continues to function with degraded performance. The result still has some utility even if late (value drops gradually). |

***

### Key Takeaway for Project Design
* **Hard Real Time** requires a **deterministic** OS (RTOS) and rigorous mathematical proof (Schedulability Analysis) to guarantee $100\%$ success.
* **Soft/Firm Real Time** can often run on general-purpose systems (like Linux) where average performance is "good enough," but worst-case scenarios are acceptable.