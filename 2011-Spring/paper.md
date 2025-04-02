# Final Exam Questions (Spring 2011)
---
## Problem 1 (24 points) Write the correct answer for each question in the following table.

---

1. **Which of the following is a legitimate difference between IA-32 and x86-64?**
   - (a) Buffer overflow exploits are impossible under x86-64.
   - (b) IA-32 has caller- and callee-saved register conventions, while x86-64 does not.
   - (c) Under x86-64, any instructions that take 32-bit operands are illegal.
   - (d) None of the above.
---
2. **Which of the following is the best justification for using the middle bits of an address as the set index into a cache rather than the most significant bits?**
   - (a) Indexing with the most significant bits would necessitate a smaller cache than is possible with middle-bit indexing, resulting in generally worse cache performance.
   - (b) It is impossible to design a system that uses the most significant bits of an address as the set index.
   - (c) The process of determining whether a cache access will result in a hit or a miss is faster using middle-bit indexing.
   - (d) A program with good spatial locality is likely to make more efficient use of the cache with middle-bit indexing than with high-bit indexing.
---
3. **Which of the following is not true about POSIX-style signals?**
   - (a) Certain signals cannot be blocked.
   - (b) A process can send a signal to itself.
   - (c) A signal handler executing as the result of a received signal can never be interrupted by another incoming signal.
   - (d) Signals can only be delivered when returning from system mode.
---
4. **Which of the following is not a benefit of virtual memory?**
   - (a) It allows the virtual address space to be larger than the physical address space.
   - (b) No process can accidentally access the memory of another process.
   - (c) The TLB is more effective since without it dereferencing a virtual address now requires two or more memory accesses.
   - (d) Different processes can have overlapping virtual address spaces without conflict.
---
5. **Which of the following is a difference between blocking and ignoring a signal?**
   - (a) Once a blocked signal is unblocked, it will be handled by the process. A signal that comes while it is being ignored will never be handled.
   - (b) SIGSTOP and SIGINT can be ignored, but not blocked.
   - (c) Ignoring a signal only causes it to have no effect, while blocking a signal returns the signal to its sender.
   - (d) None of the above.
---
6. **Where is the first argument to a function located in 32-bit assembly code, immediately after the call instruction is executed?**
   - (a) %ebp + 0x4
   - (b) %ebp - 0x4
   - (c) %esp + 0x4
   - (d) %exp - 0x4
---
7. **Consider the following piece of code, where out.txt's contents are "abc":**

   ```c
   int main(int argc, char** argv)
   {
       int fd = open("out.txt", O_RDWR);
       char str[] = "xyz";
       char c;
       
       write(fd1, str, 1);
       read(fd1, &c, 1);
       write(fd1, &c, 1);
       return 0;
   }
   ```

   **What is the contents of out.txt after the code is run? (Assume all system calls succeed.)**
   - (a) xbb
   - (b) xba
   - (c) xac
   - (d) boat
---
8. **Which of the following is the best reason to choose FastCGI over CGI?**
   - (a) Superior support by web servers like Apache.
   - (b) Lower process creation costs.
   - (c) Lower process communication costs.
   - (d) Better process locality (all tasks can be executed locally).
---
9. **Which of the following system calls can fail due to a network failure?**
   - (a) socket(...)
   - (b) listen(...)
   - (c) bind(...)
   - (d) gethostbyname(...)
---
10. **Which of the following are copied on fork and preserved on exec?**
    - (a) Global variables.
    - (b) File descriptor tables.
    - (c) Open file entry structs.
    - (d) None of the above.
---
11. **Why would the kernel designer opt for a 2-level page table when a full 2-level page table takes up more memory than a full 1-level page table?**
    - (a) 2-level tables can translate virtual addresses faster.
    - (b) 2-level tables can reference more memory than 1-level tables.
    - (c) Most of the time, a 2-level page table will take up less memory than a 1-level page table.
    - (d) They wouldn't. Adding more tables offers no advantages.
---
12. **What section of memory holds the assembly for printf?**
    - (a) Stack
    - (b) Kernel memory
    - (c) Shared libraries
    - (d) Heap
---
13. **Every thread has its own**
    - (a) Heap
    - (b) Global values
    - (c) Stack
    - (d) Text data
---
14. **Why is gethostbyname not thread safe?**
    - (a) Only one thread at a time can do a DNS lookup.
    - (b) It doesn't have a mutex around it.
    - (c) It returns a pointer to global shared memory.
    - (d) It shares instructions with other threads.
---
15. **If a page table on a 32-bit system is 2KB in size, how many entries does it contain?**
    - (a) 2048
    - (b) 1024
    - (c) 512
    - (d) 256
---
16. **What is the function of the TLB?**
    - (a) Caches data.
    - (b) Caches instructions.
    - (c) Caches translation of virtual addresses.
    - (d) Translates physical addresses to virtual addresses.
---
17. **What is distinctive about superscalar processors?**
    - (a) Can run at frequencies over 3.5GHz.
    - (b) Can address over 4GB of memory.
    - (c) Can perform more than one instruction per cycle.
    - (d) Can have more than 2 levels of cache.
    - (e) Have more than one core per processor.
---
18. **True/False: When requested to send 20 bytes over a network socket, execution will block until all 20 bytes have been sent.**
    - (a) True
    - (b) False
---
19. **True/False: When printf returns, the programmer cannot be guaranteed that the data has appeared on the user's terminal.**
    - (a) True
    - (b) False
---
20. **Which of the following tools would you first use to debug an application which is exiting with the error "Segmentation fault"?**
    - (a) gdb
    - (b) strace
    - (c) strings
    - (d) objdump
---
21. **Which of the following tools would you first use to debug a network application that never appears to accept any connections?**
    - (a) gdb
    - (b) strace
    - (c) objdump
    - (d) valgrind
---
22. **Which of the following tools would you first use to debug an application which is exiting with a glibc error: double free detected?**
    - (a) gdb
    - (b) strace
    - (c) wireshark
    - (d) valgrind
---
23. **A 256-byte 4-way set associative cache with 16-byte blocks has**
    - (a) 4 sets
    - (b) 16 sets
    - (c) 64 sets
    - (d) No sets
---
24. **Imagine a floating point format with no sign bit, one exponent bit, and one fraction bit. Which of the following is not a number?**
    - (a) 00
    - (b) 01
    - (c) 10
    - (d) 11
    - (e) None of the above.