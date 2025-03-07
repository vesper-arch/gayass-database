## use debuggers for fucks sake just use em. here's why

---
For dealing with errors in a language like C that has none of the quality of life features of high level languages such as Python or JavaScript, a debugger will save your goddamn life.
Say if you are trying to deal with the infamous `segmentation fault` (for explanation of what that is go here [[What even is a segfault?]]). If you do not have a debugger, this error bluntly shows up as this:
```
> clang main.c -o myprogram
> myprogram
segmentation fault
```
As you can see, very descriptive.
No line number, no anything.
With a debugger, the program will stop right as you execute the null pointer reference, allowing you to see what actually happened.

![[Debugger Examples.png]]
Debuggers exist builtin to popular C developer environments such as CLion and Visual Studio but other standalone debuggers do exist.