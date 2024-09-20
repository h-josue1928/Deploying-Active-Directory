# Deploying-Active-Directory

Part 1
Install Active Directory
—
In domain controller go to server manager in server manager go to add roles features
![image](https://github.com/user-attachments/assets/7c47b661-da9f-4233-be1c-f87e5f67d330)
hit next until you reach server roles then check the acvive directory domain services box
![image](https://github.com/user-attachments/assets/7c5ca718-6e98-48a6-9e7f-f011f2263a23)
hit next until confirm installation selection then check restart and finish the install
![image](https://github.com/user-attachments/assets/83aa6839-7b76-4368-94ca-30e3b2f4c84c)
on the top right side click on the yellow flag then click "promote thid server to a domain controller"
![image](https://github.com/user-attachments/assets/b20353e9-4333-4135-ad9b-29413015a8ae)
in deployment configuration check "add new forest" 
in the root domain name enter "mydomain.com"
![image](https://github.com/user-attachments/assets/4d9a708a-5483-4abb-92ff-53c0c4b5f586)
go next until domain controller options enter a password in DSRM
![image](https://github.com/user-attachments/assets/cfd9fc8a-8ce1-4124-8120-0085f58e4738)
continue to prerequisites check, then install
![image](https://github.com/user-attachments/assets/972fc1a5-eac0-4681-a379-d0a87feaa22b)
Restart and then log back into DC-1 as user: mydomain.com\labuser
![image](https://github.com/user-attachments/assets/0224e2f6-81ca-4008-acec-f00e7971e374)

Create a Domain Admin user within the domain
—
In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES”
Create a new OU named “_ADMINS”
Create a new employee named “Jane Doe” (same password) with the username of “jane_admin” / Cyberlab123!
Add jane_admin to the “Domain Admins” Security Group
Log out / close the connection to DC-1 and log back in as “mydomain.com\jane_admin”
User jane_admin as your admin account from now on


Join Client-1 to your domain (mydomain.com)
—
From the Azure Portal, set Client-1’s DNS settings to the DC’s Private IP address (Already done)
From the Azure Portal, restart Client-1 (Already done)
Login to Client-1 as the original local admin (labuser) and join it to the domain (computer will restart)
Login to the Domain Controller and verify Client-1 shows up in ADUC
Create a new OU named “_CLIENTS” and drag Client-1 into there
