# LAB: Managing File Permissions in Linux
- Date Completed: 9/23/2024
- Skills: Linux CLI, file permissions, 'chmod', 'ls-la'
- Source: Google Cybersecurity Certificate

## Project Discription
The research team at this organization needed to update file and directory permissions inside the 'projects' directory to align with security policies. I used Linux commands to:
- Audit existing permissions
- Remove unauthorized write or execute access
- Lock down access to hidden and sensitive files
- Restrict access to specific users

## Tasks Completed 
### 1. **Check File and Directory Permissions**
```bash
ls -la /projects
```
- Used ls -la to list all files (including hidden) and view their permissions.
- Identified drafts/ (a directory), .project_x.txt (a hidden file), and five hidden projects

### 2. Understand Linux Permission Strings
Example:
```bash
-rw-rw-r-- 1 researcher1 research 1234 project_t.txt
```
- - = file, d = directory
- rw- (user), rw- (group), r-- (others)
- Project files were readable by all, and writable by user and group.

### 3. Remove Write Access from "Others"
```bash
chmod o-w project_k.txt
ls -la
```
- Removed write access from "others" on project_k.txt

### 4. Restrict Hidden File Access (.project_x.txt)
```bash
chmod u-w .project_x.txt
chmod g-w .project_x.txt
chmod g+r .project_x.txt
```
- Removed write access from user and group.
- Ensured group still had read access.

### 5. Restrict Directory Access to One User 
```bash
chmod g-x drafts
```
- Removed execute access from the group on the drafts/ directory
- Ensured only researcher2 retained access.

## Summary
I audited and modified Linux file and directory permissions using the CLI. THis is a critical task in hardening a system and reducing unauthorized access.
Tools used included:
- ls -la -- view file types and permissions
- chmod -- modify user/group/other permissions
- Understanding symbolic permissions (u,g,o,r,w,x)

## Tools Used
- Linux terminal (Ubuntu)
- ls,chmod
- File system permissions model
