# Final Exam MCQs (Fall 2011)
---

## Problem 1. (10 points) - General Systems Topics

Answer each question by writing your answer in the table provided.

---

### 1. Consider a direct-mapped cache memory. Which one of the following statements is true?
- (a) The cache has 1 line per set. ✅  
- (b) The cache has 1 word per block.  
- (c) The cache has 1 set per cache.  
- (d) None of the above.  

---

### 2. Which one of the following statements about cache memories is true:
- (a) Larger caches are more susceptible to capacity misses than smaller caches.  
- (b) Caches with lower associativity are more susceptible to conflict misses than those with higher associativity. ✅  
- (c) Caches with higher associativity are more susceptible to cold misses than those with lower associativity.  
- (d) None of the above.  

---

### 3. Which one of the following is NOT contained in an ELF executable file?
- (a) Machine code  
- (b) Global variables  
- (c) User stack ✅  
- (d) Symbol table  

---

### 4. Assuming no errors, which one of the following statements about `fork` is true?
- (a) Called once, returns once.  
- (b) Called once, returns twice. ✅  
- (c) Called once, returns never.  
- (d) Called twice, returns once.  
- (e) None of the above.  

---

### 5. Assuming no errors, which one of the following statements about `execve` is true?
- (a) Called once, returns once.  
- (b) Called once, returns twice.  
- (c) Called once, returns never. ✅  
- (d) Called twice, returns once.  
- (e) None of the above.  

---

### 6. Which one of the following statements about processes is false?
- (a) The operating system kernel runs as its own separate process. ✅  
- (b) Each process shares the CPU with other processes.  
- (c) Each process has its own private address space.  
- (d) The environment for a process is stored on the stack.  

---

### 7. What happens if the parent of a zombie child terminates?
- (a) The zombie child becomes a wraith and is never reaped.  
- (b) The zombie child is reaped by the init process. ✅  
- (c) The zombie child is reaped by the process with the nearest PID.  
- (d) None of the above.  

---

### 8. Suppose that the kernel delivers two `SIGCHLD` signals to the parent while the parent is not scheduled. When the kernel finally schedules the parent, how many times will the `SIGCHLD` handler be called?
- (a) None, because sending multiple signals will always crash the program.  
- (b) Exactly once, because signals are not queued. ✅  
- (c) Exactly twice, because signals are queued.  
- (d) More than twice, depending on how the handler is installed.  

---

### 9. Which one of the following statements is NOT true of storage allocators?
- (a) In the best case, coalescing with boundary tags is linear in the number of free blocks. ✅  
- (b) Seglists typically approximate best fit search.  
- (c) Payloads must be aligned to some boundary.  
- (d) Explicit lists are typically faster than implicit lists.  
- (e) None of the above.  

---

### 10. Which one of the following addresses is 8-byte aligned?
- (a) 1110110101110111₂  
- (b) 1110110101110100₂  
- (c) 1110110101110000₂ ✅  
- (d) 1110110101110110₂  
- (e) None of the above.  