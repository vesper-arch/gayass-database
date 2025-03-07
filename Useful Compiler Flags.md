Using the `clang` compiler, these are the flags that are pretty useful early on.
```bash
clang -std=c99 -fsanitize=address -Wall -Werror
```
The first argument, `-std=c99` states the version of C your file is written in, you need to specify this. Change the version used to whatever you prefer.
The `-fsanitize` flag is explained in this note here [[How to deal with memory corruption using ASan]]. In short it makes sure memory is not being misused in your program.
Next, the `Wall` argument is to turn on all compiler warnings. Compiler warnings help catch mistakes that aren't necessarily errors but can cause issues. The last argument promotes those warnings into compiler errors, meaning your project will not compile if it encounters a warning. This help catch issues early on.