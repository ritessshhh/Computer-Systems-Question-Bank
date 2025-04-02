# Final Exam Questions (Fall 2012)

## Problem 1: Multiple Choice Questions (18 points)

Answer each of the following 18 multiple-choice questions by writing your answer in the table provided.

---

### 1. Each thread has its own:
- (a) Heap  
- (b) Stack  
- (c) Global values  
- (d) Text data  

---

### 2. Simply decreasing the size of block headers used internally by malloc:
- (a) Decreases internal fragmentation  
- (b) Increases internal fragmentation  
- (c) Decreases external fragmentation  
- (d) Increases external fragmentation  

---

### 3. Which of the following statements about reader-writer locks is not true?
- (a) Many readers can hold the same rwlock at the same time  
- (b) Two writers cannot hold the same rwlock at the same time  
- (c) Many readers and exactly one writer can hold the same rwlock at the same time  
- (d) An rwlock can be used as a mutex  

---

### 4. Which of the following is the correct ordering (left-to-right) of a file’s compilation cycle?
- (a) `foo.c → foo.o → foo.s → foo`  
- (b) `foo → foo.s → foo.o → foo.c`  
- (c) `foo.c → foo.s → foo → foo.o`  
- (d) `foo.c → foo.s → foo.o → foo`  

---

### 5. Suppose an `int A` is stored at virtual address `0xff987cf0`, while another `int B` is stored at virtual address `0xff987d98`. If the size of a page is `0x1000` bytes, then A’s physical address is numerically less than B’s physical address.
- (a) Always true  
- (b) Always false  
- (c) Sometimes true, sometimes false  
- (d) Not enough information  

---

### 6. Assuming no errors, which one of the following functions returns exactly once?
- (a) `fork()`  
- (b) `execve()`  
- (c) `exit()`  
- (d) `longjmp()`  
- (e) `waitpid()`  

---

### 7. On a 64-bit system, which of the following C expressions is equivalent to `(x[2] + 4)[3]`, assuming `x` is declared as `int **x`?
- (a) `*((*(x + 16)) + 28)`  
- (b) `*((*(x + 2)) + 7)`  
- (c) `**(x + 28)`  
- (d) `*(((*x) + 2) + 7)`  
- (e) `(**(x + 2) + 7)`  

---

### 8. When can short counts occur?
- (a) When an EOF is encountered during a read  
- (b) When a short `int` is used as a counter  
- (c) When reading or writing to disk files  
- (d) When the kernel runs out of kernel memory  

---

### 9. A program blocks `SIGCHLD` and `SIGUSR1`, then receives a `SIGCHLD`, a `SIGUSR1`, and another `SIGCHLD` in that order. What signals does the program receive after unblocking both signals?
- (a) None, since the signals were blocked they are all discarded.  
- (b) Just a single `SIGCHLD`, since all subsequent signals are discarded.  
- (c) Just a single `SIGCHLD` and a single `SIGUSR1`, since the extra `SIGCHLD` is discarded.  
- (d) All 3 signals, since no signals are discarded.  

---

### 10. Which of the following events does not generate a signal?
- (a) Division by zero  
- (b) A new connection arrives on a listening socket  
- (c) A write is attempted on a disconnected socket  
- (d) NULL is dereferenced  
- (e) A process whose parent has already terminated exits  

---

### 11. How many integers can be stored in a cache line on an x86-64 system with a 4KB cache, 4-way set-associative, and 4 sets?
- (a) 8  
- (b) 16  
- (c) 32  
- (d) 64  
- (e) 128  

---

### 12. Which types of locality are leveraged by virtual memory?
- (a) Spatial locality  
- (b) Temporal locality  
- (c) Prime locality  
- (d) Both (a) and (b)  
- (e) Both (b) and (c)  

---

### 13. Which of the following is not a section of an ELF file?
- (a) `.text`  
- (b) `.static`  
- (c) `.rodata`  
- (d) `.data`  
- (e) `.bss`  

---

### 14. Choose the true statement:
- (a) All thread-safe functions are reentrant.  
- (b) Some reentrant functions are not thread-safe.  
- (c) It is never a good idea to use persistent state across multiple function calls.  
- (d) It is impossible to have a race condition between two threads as long as they have no shared state.  
- (e) All functions which call non-thread-safe functions are themselves not thread-safe.  

---

### 15. Why do we use dynamic memory?
- (a) The heap is significantly faster than the stack.  
- (b) The stack is prone to corruption from buffer overflows.  
- (c) Storing data on the stack requires knowing the size of that data at compile time.  
- (d) None of the above.  

---

### 16. Consider the following code:

```c
char c;
int fd1 = open("foo.txt", O_RDONLY);
int fd2 = open("foo.txt", O_RDONLY);
if (!fork()) {
   read(fd1, &c, 1);
}
```

After the child process reads a character, which is true in the parent?
- (a) `fd1` and `fd2` both point to the first character.  
- (b) `fd1` and `fd2` both point to the second character.  
- (c) `fd1` points to the first character while `fd2` points to the second character.  
- (d) `fd2` points to the first character while `fd1` points to the second character.  

---

### 17. Which of the following is true about races?
- (a) A race occurs when the correctness of the program depends on one thread reaching point A before another thread reaches point B.  
- (b) Exclusive access to all shared resources eliminates race conditions.  
- (c) Race conditions are the same as deadlocks.  
- (d) All race conditions occur inside loops.  

---

### 18. What will happen when you compile, link, and run the given code?
- (a) It will fail to compile.  
- (b) It will fail to link.  
- (c) It will raise a segmentation fault.  
- (d) It will print "0".  
- (e) It will print "1".  
- (f) It will sometimes print "0" and sometimes print "1".  