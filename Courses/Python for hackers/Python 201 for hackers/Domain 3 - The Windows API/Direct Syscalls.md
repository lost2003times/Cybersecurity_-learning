___
- Assembly is a very low level programming language
- Work directly with registers and interrupts
- Each line usually translates to one processor instruction
- Different processors use different assembly languages
- Every native API call has a p\specific number that represents it(syscall)
- Syscall numbers differ between different version of Windows
- Numbers can be verified with a debugger, or just use public lists
- To make a syscall, need to move the number to a register
- In ×64, the syscall instruction will then enter kernel mode

