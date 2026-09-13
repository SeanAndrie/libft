*This project has been created as part of the 42 curriculum by sgadinga*

# libft

A from-scratch reimplementation of the standard C library, built as the first
42 School project. It produces the static library `libft.a` and is the
foundation used by every subsequent project in the Cursus. All code follows the
42 Norm and makes no use of any forbidden libc functions beyond `write`,
`malloc` and `free`.

## Features

The library is organised in three groups:

- **Mandatory (25 functions)** — reimplementations of libc, split into
  *character checks* (`ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`,
  `ft_isprint`, `ft_toupper`, `ft_tolower`), *string handling* (`ft_strlen`,
  `ft_strlcpy`, `ft_strlcat`, `ft_strchr`, `ft_strrchr`, `ft_strncmp`,
  `ft_strnstr`, `ft_strdup`), *memory handling* (`ft_memset`, `ft_bzero`,
  `ft_memcpy`, `ft_memmove`, `ft_memchr`, `ft_memcmp`, `ft_calloc`), and
  *utility functions* (`ft_atoi`, `ft_itoa`).
- **Additional (11 functions)** — functions not present in libc: `ft_substr`,
  `ft_strjoin`, `ft_strtrim`, `ft_split`, `ft_strmapi`, `ft_striteri`,
  `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd`.
- **Bonus (9 functions)** — a small linked-list API on top of the `t_list`
  struct: `ft_lstnew`, `ft_lstadd_front`, `ft_lstsize`, `ft_lstlast`,
  `ft_lstadd_back`, `ft_lstdelone`, `ft_lstclear`, `ft_lstiter`, `ft_lstmap`.

## Build & usage

Compile the library with `make`:

```sh
make         # build libft.a (mandatory)
make bonus   # add the linked-list functions to libft.a
make test    # build and run a local test binary (libft_test)
make clean   # remove object files
make bclean  # remove bonus object files
make fclean  # remove object files and the library
make re      # fclean + all
```

To use it in your own code, include the header and link the library:

```c
#include "libft.h"

int main(void)
{
    char **words = ft_split("the  grid", ' ');
    return (0);
}
```

```sh
cc main.c libft.a -o program
```

## Repository structure

| File               | Purpose                                          |
| ------------------ | ------------------------------------------------ |
| `libft.h`          | Public prototypes and the `t_list` struct.       |
| `ft_is*.c`         | Character classification functions.              |
| `ft_str*.c`        | String manipulation and search functions.        |
| `ft_mem*.c`        | Memory manipulation and search functions.        |
| `ft_atoi.c`/`ft_itoa.c` | Conversion between strings and integers.     |
| `ft_split.c`       | Splits a string into an array of words.          |
| `ft_lst*.c`        | Linked-list construction and manipulation.       |