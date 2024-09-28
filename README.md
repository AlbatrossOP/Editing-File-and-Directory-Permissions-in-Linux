<h1>Editing File and Directory Permissions in Linux</h1>

<h2>Description</h2>
In this lab, I update permissions for certain fies and directories whithin the "Projects" directory. Checking and updating these permissions help keep the system secure.

<h2>Languages and Utilities Used</h2>

- <b>Linux CLI</b> 

<h2>Environments Used </h2>

- <b>Linux </b>

<h2>Lab walk-through:</h2>

<p align="center">
Checking File and Directory Details: <br/>

The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.

<img src="https://i.imgur.com/UT4txK9.png" height="80%" width="80%" alt="Checking File and Directory Details"/>
<br />
The first line of the screenshot displays the command I entered, and the other lines display the output. The code lists all contents of the "projects" directory. I used the "ls" command with the "-la" option to display a detailed listing of the file contents that also returned hidden files. The output of my command indicates that there is one directory named "drafts", one hidden file named ".project_x.txt", and five other project files. The 10-character string in the first column represents the permissions set on each file or directory.
<br />
<p align="center">
Changing File Permissions:  <br/>
"other" shouldn't have write access to any of their files. To comply with this, I referred to the file permissions that I previously returned. I determined project_k.txt must have the write access removed for other. The following code demonstrates how I used Linux commands to do this:

<img src="https://i.imgur.com/NHnp6ea.png" height="80%" width="80%" alt="Changing File Permissions"/>
<br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The "chmod" command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write permissions from other for the "project_k.txt" file. After this, I used "ls -la" to review the updates I made.
<br />
<p align="center">
Changing Permissions on Hidden Files: <br/>

In this scenario, "project_x.txt" has recently been archived. I do not want anyone to have write access to this project, but the user and group should have read access. The following code demonstrates how I used Linux commands to change the permissions:

<img src="https://i.imgur.com/V341Qdz.png" height="80%" width="80%" alt="Changing Permissions on Hidden Files"/>
<br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know ".project_x.txt" is a hidden file because it starts with a period (.). In this example, I removed write permissions from the user and group, and added read permissions to the group. I removed write permissions from the user with "u-w". Then, I removed write permissions from the group with "g-w", and added read permissions to the group with "g+r". 
<br />
<p align="center">
Chaning Directory Permissions:  <br/>
I only want the "researcher2" user to have access to the "drafts" directory and its contents. This means that no one other than "researcher2" should have execute permissions. The following code demonstrates how I used Linux commands to change the permissions:


<img src="https://i.imgur.com/VUWVFV4.png" height="80%" width="80%" alt="Chaning Directory Permissions"/>
<br />

The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I previously determined that the group had execute permissions, so I used the "chmod" command to remove them. The "researcher2" user already had execute permissions, so they did not need to be added.
<br />

<h2>Summary</h2>
I changed multiple permissions to match the level of authorization needed for files and directories in the projects directory to maintain good security posture. The first step in this was using "ls -la" to check the permissions for the directory. This informed my decisions in the following steps. I then used the "chmod" command multiple times to change the permissions on files and directories.

