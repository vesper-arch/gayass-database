To avoid what is called "include hell" while building a C project with multiple files, a strategy called Unity Build solves this quite easily and with no complexity.
To understand why this works, you need to understand how the `#include` instruction does. All it does is literally read the file from disk and then paste it in right after the include.
With this in mind you can implement a structure like this.
![[Unity Build Diagram.png]]
*Taken from Nic Barker's Tips for C Programming video. Timestamp 11:26*

All you do is make a `main.c` file that just includes the other files one after the other.
Do this. This can also avoid even having to use a build system like cmake or ninja since you can just compile that main.c file and sidestep all of the trouble that using a build system comes with.