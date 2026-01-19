# File-handling-project-with-python
created a simple command-line file management system that allows users to create, read, update, and delete files.

Core Functions
1. readfielandfolder()
pythonpath = Path('')
items = list(path.rglob('*'))
for i, items in enumerate(items):
    print(f"{i+1}  : {items} ")

Creates a Path object pointing to the current directory ('')
Uses rglob('*') to recursively find all files and folders
Lists them with numbered indices
Note: There's a bug here - the loop variable items shadows the list variable

2. createfile()

Shows all existing files/folders
Prompts user for a filename
Checks if file already exists using p.exists()
If new, creates the file and writes user input to it
Includes error handling with try-except

3. readfile()

Displays all files/folders
Asks which file to read
Verifies the file exists and is actually a file (not a folder)
Opens and prints the file contents
Handles errors gracefully

4. updatefile()
Provides three update options:

Option 1: Rename the file using p.rename()
Option 2: Overwrite file contents (open with 'w' mode)
Option 3: Append to file contents (open with 'a' mode)

5. deletefile()

Lists files/folders
Prompts for filename to delete
Verifies file exists before deletion
Uses os.remove() to delete the file

Main Program Flow
The script presents a menu:

Create file
Read file
Update file
Delete file

## **Complete Program Flow Diagram**
```
START
  ↓
Display Menu
  ↓
User enters choice (1-4)
  ↓
  ├─ 1 → createfile()
  │       ↓
  │   Show files → Get name → Check exists → Create & Write
  │
  ├─ 2 → readfile()
  │       ↓
  │   Show files → Get name → Check exists → Read & Display
  │
  ├─ 3 → updatefile()
  │       ↓
  │   Show files → Get name → Choose update type → Perform update
  │
  └─ 4 → deletefile()
          ↓
      Show files → Get name → Check exists → Delete
  ↓
END
