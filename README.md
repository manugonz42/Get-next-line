# Get Next Line - 42 Project

## Description
Get Next Line is a project at 42 that focuses on reading a line from a file descriptor. The objective is to develop a function that reads a line from a file, manages multiple file descriptors, and handles varying buffer sizes efficiently. This project enhances skills in file I/O, memory management, and handling different edge cases.

## Features
- Reads a line from a given file descriptor
- Handles multiple file descriptors simultaneously
- Manages dynamic memory allocation efficiently
- Works with different buffer sizes

## Usage
Clone the repository
```bash
git clone git@github.com:manugonz42/Get-next-line.git
```
Use the function in your own projects by including the files.

## Main example
```c
#include "get_next_line.h"

int main(void)
{
    int fd;
    char *line;

    // Abre el archivo que deseas leer
    fd = open("example.txt", O_RDONLY);
    if (fd == -1)
    {
        perror("Error al abrir el archivo");
        return (1);
    }

    // Lee y procesa las líneas utilizando get_next_line
    while ((line = get_next_line(fd)) != NULL)
    {
        // Procesa la línea
        printf("%s\n", line);

        // Libera la memoria asignada a la línea
        free(line);
    }

    // Cierra el archivo
    close(fd);

    return (0);
}
