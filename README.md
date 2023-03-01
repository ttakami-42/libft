# libft

## What is Libft?

At _42_, students are not allowed to use standard C functions. Therefore, they must re-create _libc_ functions and also create new additional functions needed to write complex programs. __Libft__ is the project for this purpose.

## Usage

	make
without bonus functions.

	make bonus
to compile with bonuses.

This will add _libft.a_ to your __Libft__ directory.

| Program name | libft.a |
| :--- | :--- |
| Turn in files | Makefile, libft.h, ft_*.c |
| Makefile | NAME, all, clean, fclean, re |
| External functions | Detailed below |

## Requirement
* Declaring global variables is forbidden.
* If you need helper functions to split a more complex function, define *them as static functions. This way, their scope will be limited to the appropriate file.
* Place all your files at the root of your repository.
* Turning in unused files is forbidden.
* Every .c files must compile with the flags -Wall -Wextra -Werror.
* You must use the command ar to create your library. Using the libtool command is forbidden.
* Your libft.a has to be created at the root of your repository.
* To begin, you must redo a set of functions from the libc. Your functions will have the same prototypes and implement the same behaviors as the originals. They must comply with the way they are defined in their man. The only difference will be their names. They will begin with the _ft\__ prefix. For instance, strlen becomes _ft\_strlen_.

!!! Warning
 Some of the functions' prototypes you have to redo use the restrict qualifier. This keyword is part of the c99 standard. It is therefore forbidden to include it in your own prototypes and to compile your code with the -std=c99 flag.

## Bonus requirement
* Functions to manipulate memory and strings are very useful. But you will soon discover that manipulating lists is even more useful. 
* You have to use the following structure to represent a node of your list. Add its declaration to your libft.h file:

		typedef struct s_list
		{
			void *content;
			struct s_list *next;
		}	t_list;

* The members of the t_list struct are:
	* content: The data contained in the node. void * allows storing any kind of data.
	* next: The address of the next node, or NULL if the next node is the last one.
* In your Makefile, add a make bonus rule to add the bonus functions to your libft.a.