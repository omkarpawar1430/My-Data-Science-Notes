
Tags: #python 

------------------------------------------
### Why we neen Virtual Enviroments?:

`venv` is a built-in Python library that is used to create and manage virtual environments for Python projects. A virtual environment is a self-contained directory that contains a specific version of Python along with all the libraries and dependencies required by the project. Here are some of the main uses of `venv`:

1.  Isolation: A virtual environment allows you to create an isolated environment for your Python project that is independent of any other Python projects or system-level Python installations. This helps to avoid conflicts between different versions of the same library or dependency used in different projects.
    
2.  Reproducibility: By using virtual environments, you can create a reproducible environment for your project. This ensures that anyone who works on the project, including collaborators or future maintainers, can create an identical environment and reproduce the results.
    
3.  Dependency Management: Virtual environments allow you to manage dependencies on a per-project basis. You can install specific versions of libraries required for your project without affecting other projects or the system-level Python installation.
    
4.  Portability: Virtual environments can be easily moved or copied between different systems, which makes it easy to deploy your project on different machines or servers.
    

Overall, `venv` is a powerful tool for Python developers that helps to ensure that their projects are isolated, reproducible, and easy to manage. It's a good practice to use virtual environments for all your Python projects, whether big or small, to avoid potential conflicts and ensure that the project is easily reproducible.

---

### Steps to follow:

here are some useful `venv` commands that you can use on a Linux system:

1.  ==Creating a virtual environment==:

`python3 -m venv myenv`

This creates a new virtual environment called `myenv` in the current directory using the default version of Python 3.

2.  ==Activating a virtual environment==:

`source myenv/bin/activate`

This activates the virtual environment called `myenv`.

3.  ==Deactivating a virtual environment==:

`deactivate`

This deactivates the currently active virtual environment.

4.  ==Listing installed packages==:

`pip list`

This lists all the packages installed in the current virtual environment.

5.  ==Installing a package==:

`pip install package-name`

This installs a package called `package-name` in the current virtual environment.

6.  ==Installing packages from a requirements file==:


`pip install -r requirements.txt`

This installs all the packages listed in a file called `requirements.txt` in the current virtual environment.

7.  ==Exporting installed packages to a file==:

`pip freeze > requirements.txt`

This exports all the packages installed in the current virtual environment to a file called `requirements.txt`.

8.  ==Deleting a virtual environment==:

`rm -rf myenv`

This deletes the virtual environment called `myenv`.

9.  ==Checking the location of the Python executable in the virtual environment==:

`which python`

This command will print the path to the Python executable in the currently active virtual environment.

10.  ==Upgrading `pip` in the virtual environment==:

`pip install --upgrade pip`

This upgrades the `pip` package to the latest version in the current virtual environment.

11.  ==Creating a virtual environment with a specific version of Python==:

`python3.8 -m venv myenv`

This creates a new virtual environment called `myenv` using Python 3.8.

12.  ==Activating a virtual environment with the `activate.fish` script==:

`source myenv/bin/activate.fish`

This activates the virtual environment called `myenv` using the `activate.fish` script, which is used in the Fish shell.

13.  ==Creating a virtual environment with a different version of Python==:

`virtualenv -p /usr/bin/python2.7 myenv`


These are some of the most common `venv` commands that you might use on a Linux system. There are many other commands and options available, so be sure to check the official Python documentation for more information.

---------------------
#### links:
[[]]
[[]]