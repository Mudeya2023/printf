Printf Group Project
A Printf project repository for our team.

The printf() function prints output to stdout, according to format and other arguments passed to printf(). The string format consists of two types of items - characters that will be printed to the screen, and format commands that define how the other arguments to printf() are displayed. Basically, you specify a format string that has text in it, as well as "special" characters that map to the other arguments of printf().

The prototype of this function is: int _printf(const char format, ...);

This means that it has one mandatory format argument, and an extra number of arguments that can be none, or many.

Format of the format string

The format string is a character string starting and ending with double quotes. The format string is composed of zero or more directives; ordinary characters (not %), and conversion specifications, each of which results in fetching zero or more subsequent arguments.

Each conversion specification is introduced by the character % and ends with a conversion specifier. In between there may be (in this order):

/* * This Header is optional and allows you to compare the * custom _printf() function to the standard library one. */ #include <stdio.h> ` #include <limits.h> #include <stdio.h> #include "main.h"

/**
main - Entry point

Return: Always 0 */ int main(void) { int len; int len2; unsigned int ui; void *addr;

len = _printf("Let's try to printf a simple sentence.\n"); len2 = printf("Let's try to printf a simple sentence.\n"); ui = (unsigned int)INT_MAX + 1024; addr = (void *)0x7ffe637541f0; _printf("Length:[%d, %i]\n", len, len); printf("Length:[%d, %i]\n", len2, len2); _printf("Negative:[%d]\n", -762534); printf("Negative:[%d]\n", -762534); _printf("Unsigned:[%u]\n", ui); printf("Unsigned:[%u]\n", ui); _printf("Unsigned octal:[%o]\n", ui); printf("Unsigned octal:[%o]\n", ui); _printf("Unsigned hexadecimal:[%x, %X]\n", ui, ui); printf("Unsigned hexadecimal:[%x, %X]\n", ui, ui); _printf("Character:[%c]\n", 'H'); printf("Character:[%c]\n", 'H'); _printf("String:[%s]\n", "I am a string !"); printf("String:[%s]\n", "I am a string !"); _printf("Address:[%p]\n", addr); printf("Address:[%p]\n", addr); len = _printf("Percent:[%%]\n"); len2 = printf("Percent:[%%]\n"); _printf("Len:[%d]\n", len); printf("Len:[%d]\n", len2); _printf("Unknown:[%r]\n"); printf("Unknown:[%r]\n"); return (0); } `

--- # Compilation:

When you are done creating you main.c file you will need to compile it. You can use any compiler software you like, although this project was tested in GNU GCC 5.5.0 with different error flags such as:

`-Wall: Enables all the warnings about constructions.

-Wextra : Enables some extra warning flags that are not enabled by -Wall.

-Werror: Make all warnings into hard errors.

-pedantic: Issue all the mandatory diagnostics listed in the C standard.

-Wno-format: Disables warnings about printf format (so that you can try any type of format you want) in equivalence to a custom made variadic function.`

test@ubuntu:~/printf$ gcc -Wall -Wextra -Werror -pedantic -Wno-format *.c
