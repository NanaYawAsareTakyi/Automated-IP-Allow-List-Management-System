# Automated-IP-Allow-List-Management-System
This project involves developing an automated system to manage IP address allow lists. By using an algorithm, the system continuously updates the "allow_list.txt" file to ensure that only authorized IP addresses can access sensitive information, while efficiently removing any unauthorized IP addresses.

## Objective
To enhance security and manage access to sensitive information within my organization, an allow list of authorized IP addresses is maintained in the "allow_list.txt" file. This list ensures that only approved IP addresses can access the confidential content. Additionally, a remove list is used to document IP addresses that should no longer have access. To streamline this process, I developed an algorithm that automatically updates the "allow_list.txt" file by removing any unauthorized IP addresses listed in the remove list. This automation ensures efficient and accurate management of access controls, thereby safeguarding our sensitive information.

## Skills Learned
#### Network Security Management:
Understanding and implementing IP address-based access control to secure sensitive information.

#### Automation and Scripting with Python:
Developing algorithms to automate tasks, improving efficiency and reducing the likelihood of human error.

#### File Handling: 
Working with file operations to read from and write to text files.

#### Documentation:
 Maintaining clear and comprehensive records of authorized and unauthorized IP addresses, as well as documenting the development and usage of the algorithm.
 
#### Problem-Solving:
Identifying challenges in managing access control and devising automated solutions to address them.

#### Attention to Detail: 
Ensuring the accuracy of IP addresses in the allow and remove lists to maintain proper access controls.

#### Project Management: 
Planning, developing, and executing a project from concept to implementation.

#### Cybersecurity Best Practices:
Applying principles of cybersecurity to protect sensitive information and ensure compliance with organizational policies.

## Tools Used
##### Python

## Workflow
#### Open Allow List Document:
To begin with, I opened the “allow_list.txt” file. Firstly, I assigned the file name as a string to the variable “import_file”. 

This is illustrated in the image below:

![image](https://github.com/NanaYawAsareTakyi/Automated-IP-Allow-List-Management-System/assets/173400465/e3c032bd-0cf8-4a84-aac7-ce677cbc4875)

Next, I opened the file using a “with” statement in conjunction with the “open()” function. 

This is illustrated in the image below:

![image](https://github.com/NanaYawAsareTakyi/Automated-IP-Allow-List-Management-System/assets/173400465/d9d5c5c8-0886-41a4-a59d-f0d40e249a56)

The purpose of opening the “allow_list.txt” file is to gain access to its contents. The “open()” function has two parameters namely import_file and “r”. The first parameter specifies the file to be imported and the second parameter denotes the action to be taken on the imported file. In this scenario, “r” indicates that I want to read the file. The “with” keyword serves the purpose of proper management by closing the file after exiting the “with” statement. The “as” keyword is used to assign the variable name file which stores the output of the “open()” function while I work within the “with” statement.

#### Read File Contents:
To read the contents of the file, I used the “.read()” function to convert the file into a string.

This is illustrated in the image below:

![image](https://github.com/NanaYawAsareTakyi/Automated-IP-Allow-List-Management-System/assets/173400465/128ddb6b-eb16-45bc-b8fb-225adbc60cad)

The “.read()" function can be called within the body of the “with” statement when the “r” argument is used as a parameter in the “.open()” function. The “.read()” function makes it easier to read a file by converting  it into a string. To utilize this function, I applied it to the “file” variable in the “with” statement and then assigned the output to a new variable “ip_addresses”. By virtue of applying this function, the contents of the “allow_list.txt” file is converted to a string and stored in the “ip_addresses” variable allowing me to extract and organize data from it at any point in time.

#### Convert String Into List:
To allow for manipulation of data in the file, I transformed it to a list. I applied the “.split()” function to the “ip_addresses” file to convert it from a string to list. This makes it easier to remove unauthorized IP addresses from the allow list.

This is illustrated in the image below:
![image](https://github.com/NanaYawAsareTakyi/Automated-IP-Allow-List-Management-System/assets/173400465/fd069823-5afe-4c30-ba5b-72df6c36f244)

The “.split()” function separates texts by whitespaces into list elements. In this algorithm, the IP addresses stored as strings in the “ip_addresses” variable are separated by whitespaces and converted into a list of IP addresses. I then stored the list of IP addresses by reassigning them to the variable “ip_addresses”.

#### Iterate Through IP Address List:
At this stage in building my algorithm, I searched through the IP address lists to fish out unauthorized IP addresses still found in the allow list. To achieve this, I applied the “for” loop.

This is illustrated in the image below:

![image](https://github.com/NanaYawAsareTakyi/Automated-IP-Allow-List-Management-System/assets/173400465/7ceb6db5-8a66-4c84-a9f8-41d06bca8cd4)

The “for” loop applies specific code statements to all elements in a sequence. To commence this loop, the “for” keyword is stated. It is then followed by the loop variable, in this case “element’ and the keyword “in”. The “in” keyword specifies to iterate through the sequence “ip_addresses” and assign each value to the loop variable “element”.


#### Remove Unauthorized IP Addresses:
I proceeded to remove IP addresses from the allow list, “ip_addresses” that could be found in the remove list, “remove_list”.

This is illustrated in the image below:

![image](https://github.com/NanaYawAsareTakyi/Automated-IP-Allow-List-Management-System/assets/173400465/561b2e32-4939-4054-b91b-1403399a86e6)

Firstly, within the body of the “for” loop, I assessed whether the loop variable “element” could be found in the “remove_list”. Then within the body of the “if” conditional, I applied the “.remove()” function to the “ip_addresses” list while passing the variable “element” as argument. By doing so, any IP_address found in the “remove_list” would be deleted from the “ip_addresses” list.

#### Update The File With Revised List Of IP Addresses:
Finally, I needed to update the allow list document with the updated list of IP addresses. To achieve this, I had to convert the list back into a string by using the “.join()” function.

This is illustrated in the image below:

![image](https://github.com/NanaYawAsareTakyi/Automated-IP-Allow-List-Management-System/assets/173400465/e1c5d539-8bec-4699-9960-cb116e1cd44a)

This would allow me to pass it in the argument “.write()” when writing to the file “allow_list.txt”.
After this, I used a “with” statement and the “.write()” function to update the file:

This is illustrated in the image below:

![image](https://github.com/NanaYawAsareTakyi/Automated-IP-Allow-List-Management-System/assets/173400465/29211f44-6e1d-4da2-88ae-d3c92f1aaa90)


The second parameter in the “open()” function in this case is “w” , which denotes my intention to write over the contents in the file. I can call the “.write()” function in the body of the “with” statement once “w” has been passed as a parameter in the “open()” function. The “.write()” function writes string data to a specified file and overwrites any existing content.
In this scenario, my intention was to write the revised allow list as a string to the “allow_list.txt” file to prevent IP addresses removed from the allow list from accessing restricted contents. To revise the file, I appended the “.write()” function to the file object “file” identified in the “with” statement. I passed in the “ip_addresses” variable as the argument to indicate that the contents of the file specified in the “with” statement should be replaced with the data in this variable.

## Summary

I developed an algorithm to update the "allow_list.txt" file by removing unauthorized IP addresses stored in a "remove_list" variable. The algorithm involved accessing the "allow_list.txt" file to read its contents. Converting the file content into a string format for processing, and then converting this string into a list named "ip_addresses". Iterating through both the "ip_addresses" list and the "remove_list" to identify and remove unauthorized IP addresses using the ".remove()". Converting the updated "ip_addresses" list back to a string format using the .join() function. Overwriting the contents of the "allow_list.txt" file with the modified list of authorized IP addresses. 
This process ensured that the "allow_list.txt" file accurately reflected only the authorized IP addresses, effectively managing access control for sensitive information.







