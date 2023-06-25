
Tags: #python 

------------------------------------------
The OS module in Python provides a portable way of using operating system dependent functionality. It offers many useful OS functions that are used to perform OS-based tasks and get related information about operating system.

The OS module comes under Python's standard utility modules. This module offers a portable way of using operating system dependent functionality. The Python OS module lets us work with the files and directories.

Here are some of the most common OS module functions:

- **os.listdir():** This function returns a list of all the files and directories in the current directory.
- **os.mkdir():** This function creates a new directory.
```
os.mkdir(path, exist_ok=True)

exist_ok (optional) : A default value False is used for this parameter. If the target directory already exists an OSError is raised if its value is False otherwise not. For value True leaves directory unaltered.   

```
- **os.rmdir():** This function removes an empty directory.
- **os.chdir():** This function changes the current working directory.
- **os.getcwd():** This function returns the current working directory.
- **os.path.isfile():** This function checks if the given path is a file.
- **os.path.isdir():** This function checks if the given path is a directory.
- **os.path.join():** This function joins two paths together.
- **os.path.split():** This function splits a path into its directory and file components.
- **os.path.basename():** This function returns the base name of a path.
- **os.path.dirname():** This function returns the directory name of a path.
- **os.path.abspath():** This function returns the absolute path of a file or directory.
- **os.path.normpath():** This function normalizes a path.
- **os.path.expanduser():** This function expands a path that contains a user's home directory.
- **os.path.splitext():** This function splits a path into its directory, file name, and extension components.
- **os.path.getsize():** This function returns the size of a file.
- **os.path.mtime():** This function returns the last modified time of a file.
- **os.path.ctime():** This function returns the creation time of a file.
- **os.path.utime():** This function updates the last modified and creation times of a file.
- **os.path.access():** This function checks if the user has access to a file or directory.
- **os.path.chmod():** This function changes the permissions of a file or directory.
- **os.path.chown():** This function changes the owner of a file or directory.
- **os.path.mkfifo():** This function creates a named pipe.
- **os.path.mknod():** This function creates a special file.
- **os.path.symlink():** This function creates a symbolic link.
- **os.path.readlink():** This function returns the target of a symbolic link.
- **os.path.unlink():** This function removes a symbolic link.
- **os.path.rmdir():** This function removes a directory.
- **os.path.rename():** This function renames a file or directory.
- **os.path.stat():** This function returns information about a file or directory.
- **os.path.walk():** This function recursively walks through a directory tree.

The OS module is a powerful tool that can be used to interact with the operating system. It offers a wide range of functions that can be used to perform a variety of tasks.


---------------------
#### links:
[[]]
[[]]