# System Programming Final Exam MCQs (Fall 2010)

## Problem 1 (20 points)

*(Ignore the short answer portion about networking system calls.)*

The remaining questions are multiple choice. Write the correct answer for each question in the following table.

---

2. **Which of the following is NOT a universal property of reader-writer locks?**
   - (a) Readers can only look at a shared item; writers can also modify it.
   - (b) If a writer has access to the item, then no other thread also has access.
   - (c) Any number of readers can read the item at the same time.
   - (d) A writer waiting for an RW lock will get preference over subsequent read requests. ✅

---

3. **Starvation (in relation to threads) refers to:**
   - (a) A thread waiting for a lock indefinitely. ✅
   - (b) A semaphore that gets locked but the thread never unlocks it after use.
   - (c) A thread is spawned but never joins the main thread when finished.
   - (d) A process fails to spawn a new thread because it's hit the maximum number of threads allowed.

---

4. **How does x86 assembly store the return value when a function is finished?**
   - (a) The ret instruction stores it in a special retval register.
   - (b) By convention, it is always in %eax. ✅
   - (c) It is stored on the stack just above the (%ebp) of the callee.
   - (d) It is stored on the stack just above all the arguments to the function.

---

5. **In IEEE floating point, what would be an effect of allocating more bits to the exponent part by taking them from the fraction part?**
   - (a) You could represent fewer numbers, but they could be much larger.
   - (b) You could represent the same numbers, but with more decimal places.
   - (c) You could represent both larger and smaller numbers, but with less precision. ✅
   - (d) Some previously representable numbers would now round to infinity.

---

6. **Consider the following two blocks of code, found in separate files:**

   ```c
   /* main.c */
   int i = 0;
   int main()
   {
       foo();
       return 0;
   }

   /* foo.c */
   int i = 1;
   void foo()
   {
       printf("%d", i);
   }
   ```

   **What will happen when you attempt to compile, link, and run this code?**
   - (a) It will fail to compile.
   - (b) It will fail to link. ✅
   - (c) It will raise a segmentation fault.
   - (d) It will print "0".
   - (e) It will print "1".
   - (f) It will sometimes print "0" and sometimes print "1".

---

7. **Which of the following is an example of external fragmentation?**
   - (a) A malloc'ed block needs to be padded for alignment purposes.
   - (b) A user writes data to a part of the heap that isn't the payload of a malloc'ed block.
   - (c) There are many disjoint free blocks in the heap. ✅
   - (d) A user malloc's some heap space and never frees it.

---

8. **Which of the following is NOT the default action for any signal?**
   - (a) The process terminates all of its children. ✅
   - (b) The process terminates and dumps core.
   - (c) The process terminates.
   - (d) The process stops until restarted by a SIGCONT signal.

---

9. **Which of the following is FALSE concerning x86-64 architecture?**
   - (a) A double is 64 bits long.
   - (b) Registers are 64 bits long.
   - (c) Pointers are 64 bits long.
   - (d) Pointers point to locations in memory that are multiples of 64 bits apart. ✅

---

10. **Consider the following block of code:**

    ```c
    int main()
    {
        int a[213];
        int i;
        //int j = 15;
        for(i = 0; i < 213; i++)
            a[i] = i;
        return 0;
        a[0] = -1;
    }
    ```

    **Which of the following instances of "bad style" is present?**
    - (a) Dead code.
    - (b) Magic numbers.
    - (c) Poor indentation.
    - (d) All of the above. ✅

---

11. **Consider the following structure declarations on a 64-bit Linux machine.**

    ```c
    struct RECORD {
       long value2;
       double value;
       char tag[3];
    };

    struct NODE {
       int ref_count;
       struct RECORD record;
       union {
           double big_number;
           char string[12];
       } mix;
    };
    ```

    **Also, a global variable named my_node is declared as follows:**
    ```c
    struct NODE my_node;
    ```

    **If the address of my_node is 0x6008e0, what is the value of &my_node.record.tag[1]?**
    - (a) 0x6008f8
    - (b) 0x6008fa
    - (c) 0x6008f9 ✅
    - (d) 0x6008f5
    - (e) 0x6008f1

---

12. **With reference to the previous question, what is the size of my_node in bytes?**
   - (a) 48 ✅
   - (b) 44
   - (c) 40
   - (d) 42
   - (e) 50

---

13. **Which of the following x86 instructions can be used to add two registers and store the result without overwriting either of the original registers?**
    - (a) mov
    - (b) lea ✅
    - (c) add
    - (d) None of the above

---

14. **Which of these uses of caching is not crucial to program performance?**
    - (a) Caching portions of physical memory
    - (b) Caching virtual address translations
    - (c) Caching virtual addresses ✅
    - (d) Caching virtual memory pages
    - (e) None of the above (that is, they are all crucial)

---
15. **Assuming all the system calls succeed, which of the following pieces of code will print the word "Hello" to stdout?**
    - (a) 
    ```c
    int fd = open("hoola.txt", O_RDWR);
    dup2(fd, STDOUT_FILENO);
    printf("Hello");
    fflush(stdout);
    ```
    - (b)
    ```c
    int fd = open("hoola.txt", O_RDWR);
    dup2(fd, STDOUT_FILENO);
    write(STDOUT_FILENO, "Hello", 5);
    ```
    - (c) 
    ```c
    int fd = open("hoola.txt", O_RDWR);
    dup2(fd, STDOUT_FILENO);
    printf("Hello");
    ```
    - (d) ✅
    ```c
    int fd = open("hoola.txt", O_RDWR);
    dup2(STDOUT_FILENO, fd);
    write(fd, "Hello", 5);
    ```
    - (e) 
    ```c
    int fd = open("hoola.txt", O_RDWR);
    dup2(fd, STDOUT_FILENO);
    write(fd, "Hello", 5);
    ```
---

1.  **Consider the following piece of code. Note that the file name is the same for both calls to open, and assume the file one.txt exists.**
    ```c
    int fd = open("one.txt", O_RDWR);
    int fd2 = open("one.txt", O_RDONLY);
    ```
    **Which of the following statement is true?**
    - (a) fd and fd2 will share the same file offset.
    - (b) fd2 will be invalid because you cannot have two open file descriptors referring to the same file at the same time.
    - (c) Both fd and fd2 will have an initial file offset that is set to the end of the file.
    - (d) Whatever is written to the file through fd, can be read using fd2. ✅
    - (e) In total, there will be two copies of the file one.txt in memory, one associated with fd and the other with fd2. Any changes made in a copy will not be reflected in the other copy.

---

17. **In malloclab, we provided code for an implicit list allocator (the naive implementation). Many students improved this code by creating an explicit linked list of free blocks. Which of the following reason(s) explain(s) why an explicit linked list implementation has better performance?**
    
    I. Immediate coalescing when freeing a block is significantly faster for an explicit list.
    II. The implicit list had to include every block in the heap, whereas the explicit list could just include the free blocks, making it faster to find a suitable free block.
    III. Inserting a free block into an explicit linked list is significantly faster since the free block can just be inserted at the front of the list, which takes constant time.
    
    - (a) I only.
    - (b) II only. ✅
    - (c) III only.
    - (d) II and III only.
    - (e) All I, II and III.

---

18. **Suppose a local variable int my_int is declared in a function named func. Which of the following is considered safe in C?**
    - (a) func returns &my_int and the caller dereferences the returned pointer.
    - (b) func returns &my_int and the caller prints the returned pointer to the screen. ✅
    - (c) func sets the value of a global variable to &my_int and returns. The global variable is unchanged up to the point another function dereferences the global variable.
    - (d) None of the above.

---

19. **If a parent forks a child process, to which resources might they need to synchronize their access to prevent any unexpected behavior?**
    - (a) malloc'ed memory.
    - (b) stack memory.
    - (c) global variables.
    - (d) file descriptors. ✅
    - (e) None of the above.