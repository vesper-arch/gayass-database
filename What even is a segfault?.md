Segmentation faults, as it turns out, are actually pretty simple.
![[Segmentation Fault Diagram.png]]
All it means is that your program tried to **access memory that was not allocated**.
This explains why trying to read from or write to a null pointer causes a segfault. Null usually refers to 0 in memory and it is almost always invalid.