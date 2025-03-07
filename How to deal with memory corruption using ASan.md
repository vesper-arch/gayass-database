As opposed to segmentation faults, which usually are caused by accessing invalid memory, memory corruption bugs are when you end up accidentally accessing or even overwriting *other valid parts of memory* that are being used in your program. I don't know about you, but that sounds fucking aneurysm inducing.

An example of one of these memory corruption errors actually happened in the development of the first Fallout game where an array had one more element assigned than was allocated. And because the `malloc` function actually allocates slightly more than you asked for, this corruption went unnoticed until it started wreaking havoc on the rest of the program. 

Of course, this was a while ago and tools for detecting these kinds of errors were not yet developed enough to catch everything. Nowadays tools exist known as Address Sanitizers (shortened to ASan) that can catch problems related to memory corruption so they can be fixed easier.
The most popular one today was made by Google but now sanitizers are built into most modern compilers. With Clang you can turn it on with the flag `-fsanitize=address`.

The address sanitizer inserts special memory around what you are allocating for and checks when it is accessed so it can catch when you are doing something wrong.

It is worth noting that using ASan has performance impacts and should not be shipped with the program on release which means these memory issues have to be caught on your local environment while testing.