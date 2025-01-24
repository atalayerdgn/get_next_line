
# GET_NEXT_LINE

May it be a file, stdin, or even later a network connection, you will always need a way to read content line by line.

## READ()
The read function in C is a system call that allows you to read data from a file descriptor into a buffer. It is defined in <unistd.h> and is commonly used for low-level input operations

## THE STATIC KEYWORD C
The static keyword in C has several important uses, depending on the context in which it is applied:

### Static Variables in Functions:
A static variable inside a function retains its value across multiple calls to the function. It is initialized only once, and its value persists between calls.


Example:
```C
#include <stdio.h>

void counter() {
    static int count = 0; // Retains its value between function calls
    count++;
    printf("Counter: %d\n", count);
}

int main() {
    counter(); // Output: Counter: 1
    counter(); // Output: Counter: 2
    counter(); // Output: Counter: 3
    return 0;
}

```

## Example main.c


```C



#include "stdio.h"
#include "get_next_line.h"

int main(void){
    int fd = open("example.txt", O_RDONLY);
    printf("%s",get_next_line(fd)); // getting the first line
    printf("%s",get_next_line(fd)); // getting the second line
}




```
```bash
gcc *.c
./a.out
```