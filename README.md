# Project description
The research team at my organization (fictional) needs to update the file permissions for certain files and
directories within the projects directory. The permissions do not currently reflect the level of
authorization that should be given. Checking and updating these permissions will help keep
their system secure. To complete this task, I performed the following tasks:

## Checking file and directory details
The following code demonstrates how I used Linux commands to determine the existing
permissions set for a specific directory in the file system.

![image](https://github.com/mikeal-12/File-Permissions-in-Linux/assets/72464155/ea46eea0-32e7-44f5-a58e-7a861256a421)

The first line of the screenshot displays the command I entered, and the other lines display the
output. The code lists all contents of the projects directory. I used the <code> ls </code> command with the
<code> -la </code> option to display a detailed listing of the file contents that also returned hidden files.

The output of my command indicates that there is one directory named drafts, one hidden file
named <code>.project_x.txt</code>, and five other project files. The 10-character string in the first
column represents the permissions set on each file or directory.
