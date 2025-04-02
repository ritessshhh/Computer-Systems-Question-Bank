# Final Exam MCQs (Fall 2009) - Problem 1 (18 points)

---

## **A. Which of these uses of caching is not crucial to program performance?**
   (a) Caching portions of physical memory
   (b) Caching virtual memory pages
   (c) Caching virtual addresses ✅
   (d) Caching virtual address translations
   (e) None of the above (i.e., they are all crucial)

---

## **B. For which values can X not be equal to Z in the code below (circle all that apply):**
   ```c
   int X = CONSTANT;
   float Y = X;
   int Z = Y;
   ```
   (a) For large positive values of CONSTANT (e.g., >1,000,000,000) ✅
   (b) For large negative values of CONSTANT (e.g., > -100)
   (c) For small positive values of CONSTANT (e.g., < 100)
   (d) For small negative values of CONSTANT (e.g., < -1,000,000,000) ✅
   (e) None of the above (i.e., X==Z in all of these cases)

---

## **C. What is the maximum number of page faults per second that can be serviced in a system with a disk that has the following characteristics:**
   10,000 RPM rotation speed (6ms per full revolution), average seek time of 7ms, 1000 sectors per track.
   (Assume that all in-memory pages that get replaced are clean.)
   (a) 50
   (b) 100 ✅
   (c) 77
   (d) Not enough information to determine the answer

---

## **D. If a parent process forks a child process, to which resources might they need to synchronize their access to prevent unexpected behavior?**
   (a) file descriptors ✅
   (b) malloc'ed memory
   (c) stack
   (d) None of the above

---

## **E. Which of the following is not a situation that results in a signal being sent to a process?**
   (a) A process terminates
   (b) A process accesses an invalid memory address
   (c) A new connection arrives on a listening socket ✅
   (d) A divide by zero
   (e) None of the above (i.e., all result in a signal being sent)

---

## **F. Mr. Fred says that, if one of a process's memory addresses is bigger than a second one, then its corresponding value must appear before the second one's value in physical memory. True or False?**
   (a) True.
   (b) False. ✅