# libft - Custom C Library Implementation

## About

**libft** is the first project at École 42, designed to recreate essential C standard library functions from scratch. This foundational project teaches low-level programming concepts, memory management, and algorithmic thinking while establishing a personal library that will be used throughout the 42 curriculum.

The project involves implementing commonly used C functions without using the standard library, providing deep understanding of how these fundamental functions work under the hood.

## Learning Objectives

- **Memory Management**: Understanding malloc, free, and pointer manipulation
- **String Manipulation**: Implementing string functions without standard library
- **Linked Lists**: Creating and managing dynamic data structures
- **Code Standards**: Following strict coding standards (42 Norm)
- **Testing & Debugging**: Writing robust, error-free code
- **Documentation**: Creating clean, readable code with proper function documentation

## Functions Implemented

### Part 1: Libc Functions
Standard C library functions recreated with `ft_` prefix:

#### Character Classification & Conversion
- `ft_isalpha` - Check if character is alphabetic
- `ft_isdigit` - Check if character is digit
- `ft_isalnum` - Check if character is alphanumeric
- `ft_isascii` - Check if character is ASCII
- `ft_isprint` - Check if character is printable
- `ft_toupper` - Convert to uppercase
- `ft_tolower` - Convert to lowercase

#### String Functions
- `ft_strlen` - Calculate string length
- `ft_strchr` - Find first occurrence of character
- `ft_strrchr` - Find last occurrence of character
- `ft_strncmp` - Compare strings up to n characters
- `ft_strnstr` - Locate substring in string
- `ft_strlcpy` - Copy string with size limit
- `ft_strlcat` - Concatenate strings with size limit

#### Memory Functions
- `ft_memset` - Fill memory with constant byte
- `ft_bzero` - Zero a byte string
- `ft_memcpy` - Copy memory area
- `ft_memmove` - Copy memory area (handles overlap)
- `ft_memchr` - Scan memory for character
- `ft_memcmp` - Compare memory areas

#### Conversion Functions
- `ft_atoi` - Convert string to integer
- `ft_calloc` - Allocate and zero memory
- `ft_strdup` - Duplicate string

### Part 2: Additional Functions
Enhanced string manipulation functions:

- `ft_substr` - Extract substring
- `ft_strjoin` - Join two strings
- `ft_strtrim` - Trim characters from string
- `ft_split` - Split string by delimiter
- `ft_itoa` - Convert integer to string
- `ft_strmapi` - Apply function to each character
- `ft_striteri` - Apply function to each character with index
- `ft_putchar_fd` - Output character to file descriptor
- `ft_putstr_fd` - Output string to file descriptor
- `ft_putendl_fd` - Output string with newline to file descriptor
- `ft_putnbr_fd` - Output number to file descriptor

### Bonus Part: Linked List Functions
Implementation of linked list data structure and manipulation functions:

```c
typedef struct s_list
{
    void            *content;
    struct s_list   *next;
}                   t_list;
```

- `ft_lstnew` - Create new list element
- `ft_lstadd_front` - Add element to beginning of list
- `ft_lstsize` - Count elements in list
- `ft_lstlast` - Get last element of list
- `ft_lstadd_back` - Add element to end of list
- `ft_lstdelone` - Delete single list element
- `ft_lstclear` - Delete and free entire list
- `ft_lstiter` - Apply function to each list element
- `ft_lstmap` - Apply function and create new list

## Usage

### Compilation

```bash
# Compile the library
make

# Compile with bonus functions
make bonus

# Clean object files
make clean

# Clean everything
make fclean

# Recompile everything
make re
```

### Integration

```c
#include "libft.h"

int main()
{
    char *str = ft_strdup("Hello, 42!");
    char **split = ft_split("one,two,three", ',');
    
    ft_putstr_fd(str, 1);
    
    // Clean up
    free(str);
    // Free split array...
    
    return 0;
}
```

### Compilation with your project

```bash
gcc -Wall -Wextra -Werror your_file.c -L. -lft -o your_program
```

## Testing

The library has been tested with:
- Custom test suite covering edge cases
- Memory leak detection with `valgrind`
- Comparison testing against standard library functions
- Peer evaluation as part of 42 curriculum

```bash
# Example testing
gcc -Wall -Wextra -Werror tests/main.c -L. -lft -o test
./test
```

## 42 Norm Compliance

All code follows the strict 42 coding standard:
- Maximum 25 lines per function
- Maximum 80 characters per line
- Specific naming conventions
- No memory leaks
- Proper error handling

## Key Challenges & Solutions

### Memory Management
- **Challenge**: Proper allocation and deallocation without leaks
- **Solution**: Systematic approach to malloc/free pairs and careful pointer handling

### Edge Cases
- **Challenge**: Handling NULL pointers, empty strings, and boundary conditions
- **Solution**: Comprehensive input validation and defensive programming

### Performance
- **Challenge**: Creating efficient implementations
- **Solution**: Understanding algorithmic complexity and choosing optimal approaches

## Skills Demonstrated

- **Low-level Programming**: Working directly with memory and pointers
- **Algorithm Implementation**: Creating efficient, robust algorithms
- **Code Quality**: Writing clean, maintainable, and well-documented code
- **Testing**: Developing comprehensive test strategies
- **Project Management**: Using Makefiles and proper project organization

## Related Projects

This library serves as the foundation for subsequent 42 projects:
- **get_next_line**: Reading files line by line
- **ft_printf**: Custom printf implementation  
- **push_swap**: Sorting algorithm implementation
- And many more...

## Notes

Every function was implemented from scratch, providing invaluable experience in understanding how fundamental computing operations work at the lowest level.

---

*Developed as part of the École 42 curriculum - where learning happens through peer-to-peer education and project-based learning.*
