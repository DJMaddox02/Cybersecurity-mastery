# Lab: Updating an Allow List using Python Algorithm
Date Completed: 3/25/2025
Skills Practiced: File handeling in Python, list operations, data cleanup
Source: Google Cybersecurity Certificate -- Python Project

## Project Description
At this organization, access to restricted content is controlled with an allow list of IP addressess. These IPs are stored in a file named 'allow_list.txt', while a separate 'remove_list' identifies IP addresses that should no longer have access.

I created a Python algorithm to:
- Open and read the allow list
- Convert it into a list of IP addresses
- Remove any IPs found in the 'remove_list'
- Write the updated list back to the file

## Key Steps in the Algorithm
### 1. Open the Allow List File
```python 
import_file = "allow_list.txt"
with open(import_file, "r") as file:
  ip_addresses = file.read()
```
- Opened the file in read mode to access stored IPs
- Used with to ensure the file is closed automatically

### 2. Convert File Contents into a List
```python
ip_addresses = ip_addresses.split()
```
- Used .split() to turn tbe IP string into a Python list

### 3. Iterate Through the Remove List and Clean
```python
for element in remove_list:
  if element in ip_addresses:
    ip_addresses.remove(element)
```
- Used a for loop and if statement to ensure only matching IPs are removed
