The create_python_script function creates a new python script in the current working directory, adds the line of comments to it declared  by the 'comments' variable, and returns the size of the new file. 
Fill in the gaps to create a script called "program.py".

```python
import os
def create_python_script(filename):
    comments = "# Start of a new Python program\n"

    # Create the file and write the comment line
    with open(filename, "w") as file:
        file.write(comments)

    # Get the file size
    filesize = os.path.getsize(filename)

    return filesize

print(create_python_script("program.py"))
```
The new_directory function creates a new directory inside the current working directory, then creates a new empty file inside the new directory, and returns the list of files in that directory. Fill in the gaps to create a file "script.py" in the directory "PythonPrograms". 


```python
import os

def new_directory(directory, filename):
    # Before creating a new directory, check to see if it already exists
    if not os.path.isdir(directory):
        os.mkdir(directory)  # Create the directory if it doesn't exist

    # Change the working directory to the new one
    os.chdir(directory)

    # Create the new file inside the new directory
    with open(filename, "w") as file:
        pass  # Creates an empty file

    # Return the list of files in the new directory
    return os.listdir()

print(new_directory("PythonPrograms", "script.py"))

```
The file_date function creates a new file in the current working directory, checks the date that the file was modified, and returns just the date portion of the timestamp in the format of yyyy-mm-dd. Fill in the gaps to create a file called "newfile.txt" and check the date that it was modified.

```python
import os
import datetime

def file_date(filename):
    # Create the file in the current directory
    with open(filename, "w") as file:
        file.write("")  # Creates an empty file

    # Get the modification timestamp
    timestamp = os.path.getmtime(filename)

    # Convert the timestamp into a readable format, then into a string
    date_string = datetime.datetime.fromtimestamp(timestamp).strftime("%Y-%m-%d")

    # Return just the date portion
    return "{:10}".format(date_string)  # Ensures yyyy-mm-dd format

print(file_date("newfile.txt"))  
# Should be today's date in the format of yyyy-mm-dd

```
The parent_directory function returns the name of the directory that's located just above the current working directory. Remember that '..' is a relative path alias that means "go up to the parent directory". Fill in the gaps to complete this function.
```python
import os

def parent_directory():
    # Create a relative path to the parent of the current working directory
    relative_parent = os.path.join(os.getcwd(), "..")

    # Return the absolute path of the parent directory
    return os.path.abspath(relative_parent)

print(parent_directory())
```
