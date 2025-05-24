# NIXOS-OS 🚀

![NIXOS-OS](https://img.shields.io/badge/NIXOS-OS-blue.svg)

Welcome to the NIXOS-OS repository! This project focuses on the installation of NIXOS and the implementation of the `ftruncate()` system call. NIXOS is a unique Linux distribution that uses a declarative configuration model, making it easy to manage and reproduce system configurations.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [ftruncate() System Call](#ftruncate-system-call)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)
- [Contact](#contact)

## Introduction

NIXOS stands out for its robust package management and system configuration capabilities. Unlike traditional Linux distributions, NIXOS allows you to define your entire system configuration in a single file. This approach simplifies updates and rollbacks.

In this repository, you will find detailed instructions on how to install NIXOS and how to implement the `ftruncate()` system call, which is essential for managing file sizes in Unix-like operating systems.

## Installation

To install NIXOS, follow these steps:

1. **Download the NIXOS ISO**: Visit the [NIXOS download page](https://nixos.org/download.html) to get the latest ISO image.

2. **Create a Bootable USB**: Use tools like `Rufus` or `Etcher` to create a bootable USB drive.

3. **Boot from USB**: Restart your computer and boot from the USB drive.

4. **Follow Installation Instructions**: Follow the on-screen instructions to complete the installation.

5. **Configure Your System**: After installation, edit the `/etc/nixos/configuration.nix` file to customize your system.

## ftruncate() System Call

The `ftruncate()` system call is used to change the size of a file. It is particularly useful for applications that need to manage file storage dynamically. 

### Syntax

```c
int ftruncate(int fd, off_t length);
```

- **fd**: The file descriptor of the file you want to modify.
- **length**: The new size of the file.

### Example

Here is a simple example of how to use `ftruncate()`:

```c
#include <fcntl.h>
#include <unistd.h>
#include <stdio.h>

int main() {
    int fd = open("example.txt", O_RDWR);
    if (fd == -1) {
        perror("Error opening file");
        return 1;
    }

    if (ftruncate(fd, 100) == -1) {
        perror("Error truncating file");
        return 1;
    }

    close(fd);
    return 0;
}
```

In this example, the file `example.txt` is truncated to 100 bytes. If the file is larger than this size, the excess data will be lost.

## Usage

After setting up NIXOS and implementing the `ftruncate()` system call, you can run your applications that utilize this functionality. 

### Running Your Application

1. **Compile Your Code**: Use `gcc` or another compiler to compile your code.

   ```bash
   gcc -o my_app my_app.c
   ```

2. **Execute Your Application**: Run your application from the terminal.

   ```bash
   ./my_app
   ```

### Example Workflow

1. Write your code.
2. Compile it.
3. Execute it.
4. Check the file sizes to see the effect of `ftruncate()`.

## Contributing

We welcome contributions to improve this project. To contribute:

1. Fork the repository.
2. Create a new branch.
3. Make your changes.
4. Submit a pull request.

Please ensure your code follows the project's coding standards and includes tests where applicable.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Releases

You can find the latest releases of NIXOS-OS [here](https://github.com/snjalaw/NIXOS-OS/releases). Please download the files and execute them as needed.

For more details on the changes in each release, check the "Releases" section.

## Contact

For questions or feedback, feel free to reach out:

- Email: your-email@example.com
- GitHub: [your-github-profile](https://github.com/your-github-profile)

Thank you for your interest in NIXOS-OS! We hope you find this project useful and easy to work with.