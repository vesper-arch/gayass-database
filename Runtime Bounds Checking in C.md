C does not have any runtime bounds checking for objects like arrays and strings. In fact, it doesn't even have any concept of how many object are in an array which means you will have to keep track of all this information throughout the program. As it turns out, there is a pretty simple solution to implementing bounds checking.
First, define an array struct for what you want that includes the length and capacity of the array.
```c
typedef struct {
	int32_t* items;
	int32_t length;
	int32_t capacity;
} Int32Array;
```
*Yes, you do put the name of the struct after the closing brackets in C. Don't ask me why.*
These structs can be used as function arguments but there still is the problem of accessing it out of bounds.
This can be resolved by writing a get function for the array struct like this
```c
int Int32Array_Get(Int32Array array, int32_t index) {
	if (index >= 0 && index < array.length) {
		return array.items[index];
	}
	return 0;
}
```

Yes, this does mean you will have to make a new struct and get function for every type you want to use it for. As an alternative you could use a void pointer as a sort of generic type and write some macro shit to make it nice. There are also libraries that implement a generic array type like stb.