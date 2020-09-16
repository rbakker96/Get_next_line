<p align="center">
  <img src="https://github.com/rbakker96/images/blob/master/codam_logo.png">
</p>

# Get Next Line 
***The aim of this project is to make you code a function that returns a line ending with a newline, read from a file descriptor***

---

### Project summary
> 1th ring Codam project

This project will not provide a very convenient function to the collection, but it will also introduce a highly interesting new concept in C programming: static variables.

---

### Technical considerations
> The project needs to comply with the following rules/functionalities.

- Calling your function get_next_line in a loop will then allow you to read the text available on a file descriptor one line at a time until the EOF.
- Make sure that your function behaves well when it reads from a file and when it reads from the standard input.
- libft is not allowed for this project. You must add a get_next_line_utils.c file which will contain the functions that are needed for your get_next_line to work.
- Your program must compile with the flag -D BUFFER_SIZE=xx. which will be used as the buffer size for the read calls in your get_next_line. This value will be modified by your evaluators and by moulinette.
- Compilation will be done this way : gcc -Wall -Wextra -Werror -D BUFFER_SIZE=32 get_next_line.c get_next_line_utils.c
- Your read must use the BUFFER_SIZE defined during compilation to read from a file or from stdin.
- In the header file get_next_line.h you must have at least the prototype of the function get_next_line.
- We consider that get_next_line has an undefined behavior if, between two calls, the same file descriptor switches to a different file before EOF has been reached on the first fd.
- lseek is not an allowed function. File reading must be done only once.
- Finally we consider that get_next_line has an undefined behavior when reading from a binary file. However, if you wish, you can make this behavior coherent.
- Global variables are forbidden.

---

### Usage
> Create a main to use the get_next_line function, for example this main print the written lines 

```javascript
int	main(int argc, char **argv)
{
	int		fd;
	char	*line;

	if (argc || argv)
		;
	fd = open(argv[1], O_RDONLY);
	while (get_next_line(fd, &line) == 1)
		printf("%s\n", line);
	close(fd);
	return (0);
}
```

> Create a test text file 

> Run the following commands in the terminal

```shell
$ git clone https://github.com/rbakker96/get_next_line gnl
$ cd gnl
$ make
$ gcc -Wall -Wextra -Werror -D BUFFER_SIZE=32 main.c libgnl.a
$ ./a.out <test file>
```

---

### Used resources
> Most noteworthy resources used during this project

- <a href="https://www.geeksforgeeks.org/input-output-system-calls-c-create-open-close-read-write/" target="_blank">File Descripter / open / read</a>
- <a href="https://www.geeksforgeeks.org/static-variables-in-c/" target="_blank">Static Variables in C</a>
