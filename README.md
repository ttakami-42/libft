# libft

## What is Libft?

__This is the first task for 42 common core circle.__

* At _42_, students are not allowed to use standard C functions. Therefore, they must re-create _libc_ functions and also create new additional functions needed to write complex programs. __Libft__ is the project for this purpose.

	| Program name   | libft.a                      |
	| :------------- | :--------------------------- |
	| Turn in files  | Makefile, libft.h, ft_*.c    |
	| Makefile       | NAME, all, clean, fclean, re |
	| External funcs | Detailed below               |

## Usage

	make
without bonus functions.


	make bonus
to compile with bonuses.

Those commands will add _libft.a_ to your __Libft__ directory.
## Requirement
* Declaring global variables is forbidden.
* If you need helper functions to split a more complex function, define *them as static functions. This way, their scope will be limited to the appropriate file.
* Place all your files at the root of your repository.
* Turning in unused files is forbidden.
* Every .c files must compile with the flags -Wall -Wextra -Werror.
* You must use the command ar to create your library. Using the libtool command is forbidden.
* Your libft.a has to be created at the root of your repository.

### Libc funcs
* To begin, you must redo a set of functions from the libc. Your functions will have the same prototypes and implement the same behaviors as the originals. They must comply with the way they are defined in their man. The only difference will be their names. They will begin with the _ft\__ prefix. For instance, strlen becomes _ft\_strlen_.

	function name | lib name where the original | external func
	:------------ | :-------------------------: | :-----------:
	ft_isalpha    | ctypes.h                    | None
	ft_isdigit    | ctypes.h                    | None
	ft_isalnum    | ctypes.h                    | None
	ft_isascii    | ctypes.h                    | None
	ft_isprint    | ctypes.h                    | None
	ft_toupper    | ctypes.h                    | None
	ft_tolower    | ctypes.h                    | None
	ft_memset     | string.h                    | None
	ft_bzero      | string.h                    | None
	ft_memcpy     | string.h                    | None
	ft_memmove    | string.h                    | None
	ft_memchr     | string.h                    | None
	ft_memcmp     | string.h                    | None
	ft_strlen     | string.h                    | None
	ft_strdup     | string.h                    | malloc
	ft_strncpy    | string.h                    | None
	ft_strlcat    | string.h                    | None
	ft_strchr     | string.h                    | None
	ft_strrchr    | string.h                    | None
	ft_strstr     | string.h                    | None
	ft_strnstr    | string.h                    | None
	ft_strncmp    | string.h                    | None
	ft_atoi       | string.h                    | None
	ft_calloc     | stdlib.h                    | malloc

**Warning**
Some of the functions' prototypes you have to redo use the restrict qualifier. This keyword is part of the c99 standard. It is therefore forbidden to include it in your own prototypes and to compile your code with the `-std=c99` flag.

### Additional funcs
* In this part, you must develop a set of functions that are either not in the libc, or that are part of it but in a different form.

**Note**
* Some of the following functions can be useful for writing the functions of Part 1.

	function name | Description | external func
	:------------ | :---------- | :-----------:
	ft_substr     | Allocates (with malloc) and returns a substring from the first string given as a parameter. The substring begins at index (second parameter) and is of maximum size (thrid parameter). | malloc
	ft_strjoin    | Allocates (with malloc) and returns a new string, which is the result of the concatenation of two string parameters. | malloc
	ft_strtrim    | Allocates (with malloc) and returns a copy of first string parameter with the characters specified in second parameter removed from the beginning and the end of the string. | malloc
	ft_split      | Allocates (with malloc) and returns an array of strings obtained by splitting string parameter using the character parameter as a delimiter. The array must end with a NULL pointer. | malloc, free
	ft_itoa       | Allocates (with malloc) and returns a string representing the integer received as an parameter. Negative numbers must be handled. | malloc
	ft_strmapi    | Applies the function given as a parameter to each character of the string given as a parameter, and passing its index as first argument to create a new string (with malloc) resulting from successive applications of function. | malloc
	ft_striteri   | Applies the function given as a parameteron each character of the string passed as argument, passing its index as first argument. Each character is passed by address to function to be modified if necessary. | None
	ft_putchar_fd | Outputs the character given as a parameter to the given file descriptor. | write
	ft_putstr_fd  | Outputs the string given as a parameter to the given file descriptor. | write
	ft_putendl_fd | Outputs the string given as a parameter to the given file descriptor followed by a newline. | write
	ft_putnbr_fd  | Outputs the integer given as a parameter to the given file descriptor. | write

## Bonus requirement
* Functions to manipulate memory and strings are very useful. But you will soon discover that manipulating lists is even more useful. 

_You have to use the following structure to represent a node of your list. Add its declaration to your libft.h file:_

	typedef struct s_list
	{
		void		*content;
		struct s_list	*next;
	}			t_list;

* The members of the t_list struct are:
	* content: The data contained in the node. void * allows storing any kind of data.
	* next: The address of the next node, or NULL if the next node is the last one.
* In your Makefile, add a make bonus rule to add the bonus functions to your libft.a.

### Bonus funcs

	function name | Description | external func
	:------------ | :---------- | :-----------:
	ft_lstnew       | Allocates (with malloc) and returns a new node. | malloc
	ft_lstadd_front | Adds the node ’new’ at the beginning of the list. | None
	ft_lstsize      | Counts the number of nodes in a list. | None
	ft_lstlast      | Returns the last node of the list. | None
	ft_lstadd_back  | Adds the node ’new’ at the end of the list. | None
	ft_lstdelone    | Takes as a parameter a node and frees the memory of the node’s content using the function given as a parameter and free the node. The memory of ’next’ must not be freed. | None
	ft_lstclear     | Deletes and frees the given node and every successor of that node, using the function given as a parameter and free. Finally, the pointer to the list must be set to NULL. | free
	ft_lstiter      | Iterates the list and applies the function on the content of each node. | None
	ft_lstmap       | Iterates the list and applies the function on the content of each node. This function takes the addresses of two functions as args. | malloc, free

_Boys will Be Boys, but..._