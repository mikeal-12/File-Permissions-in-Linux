# Project description
The research team at my organization (fictional) needs to update the file permissions for certain files and
directories within the projects directory. The permissions do not currently reflect the level of
authorization that should be given. Checking and updating these permissions will help keep
their system secure. To complete this task, I performed the following tasks:

## Checking file and directory details
The following code demonstrates how I used Linux commands to determine the existing
permissions set for a specific directory in the file system.

![image](https://github.com/mikeal-12/File-Permissions-in-Linux/assets/72464155/1bad6bcc-7e06-4828-8808-140cfc397c4f)


The first line of the screenshot displays the command I entered, and the other lines display the
output. The code lists all contents of the projects directory. I used the <code> ls </code> command with the
<code> -la </code> option to display a detailed listing of the file contents that also returned hidden files.

The output of my command indicates that there is one directory named <code> drafts </code>, one hidden file
named <code>.project_x.txt</code>, and five other project files. The 10-character string in the first
column represents the permissions set on each file or directory.

## Describing the permissions string
The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:
-	1st character: This character is either a <code>d</code> or hyphen <code>-</code> and indicates the file type. If it’s a <code>d</code>, it’s a directory. If it’s a hyphen <code>-</code>, it’s a regular file.

-	2nd-4th characters: These characters indicate the read <code>r</code>, write <code>w</code>, and execute <code>x</code> permissions for the user. When one of these characters is a hyphen <code>-</code> instead, it indicates that this permission is not granted to the user.

-	5th-7th characters: These characters indicate the read <code>r</code>, write <code>w</code>, and execute <code>x</code> permissions for the group. When one of these characters is a hyphen <code>-</code> instead, it indicates that this permission is not granted for the group.
-	8th-10th characters: These characters indicate the read <code>r</code>, write <code>w</code>, and execute <code>x</code> permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen <code>-</code> instead, that indicates that this permission is not granted for other.

For example, the file permissions for <code>project_t.txt</code> are <code>-rw-rw-r--</code>. Since the first character is a hyphen <code>-</code>, this indicates that <code>project_t.txt</code> is a file, not a directory. The second, fifth, and eighth characters are all <code>r</code>, which indicates that user, group, and other all have read permissions. The third and sixth characters are <code>w</code>, which indicates that only the user and group have write permissions. No one has execute permissions for <code>project_t.txt</code>.

## Changing file permissions
The organization determined that other shouldn't have write access to any of their files. To comply with this, I referred to the file permissions that I previously returned. I determined <code>project_k.txt</code> must have the write access removed for other.

The following code demonstrates how I used Linux commands to do this:

![image](https://github.com/mikeal-12/File-Permissions-in-Linux/assets/72464155/5b3b92e2-e4a3-41af-b645-87af54b268bf)

The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The <code>chmod</code> command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write permissions from other for the <code>project_k.txt</code> file. After this, I used <code>ls -la</code> to review the updates I made.

## Change file permissions on a hidden file
The research team at my organization recently archived <code>project_x.txt</code>. They do not want anyone to have write access to this project, but the user and group should have read access. 

The following code demonstrates how I used Linux commands to change the permissions:

![image](https://github.com/mikeal-12/File-Permissions-in-Linux/assets/72464155/84f85cab-d543-440f-8f9b-18dd69d1c5ab)

The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know .<code>project_x.txt</code> is a hidden file because it starts with a period <code>.</code> . In this example, I removed write permissions from the user and group, and added read permissions to the group. I removed write permissions from the user with <code>u-w</code>. Then, I removed write permissions from the group with <code>g-w</code>, and added read permissions to the group with <code>g+r</code>

## Change directory permissions
My organization only wants the <code>researcher2</code> user to have access to the drafts directory and its contents. This means that no one other than <code>researcher2</code> should have execute permissions.

The following code demonstrates how I used Linux commands to change the permissions:

![image](https://github.com/mikeal-12/File-Permissions-in-Linux/assets/72464155/e51ade96-355f-4a83-b7f3-e6651112c59e)











