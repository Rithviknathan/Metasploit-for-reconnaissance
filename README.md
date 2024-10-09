# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find out the ip address of the attackers system

## OUTPUT:
![1](https://github.com/user-attachments/assets/d77b82f5-80a2-4278-8385-53892f36a35f)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:

systemctl start postgresql

msfdb init

Invoke msfconsole:
## OUTPUT:
![2](https://github.com/user-attachments/assets/b8bf9cbb-7412-4faa-b946-96ab879413d6)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![3](https://github.com/user-attachments/assets/7f0e6f75-d936-435b-8525-360d30f78ba6)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

### OUTPUT:
![4](https://github.com/user-attachments/assets/740aa286-edc7-442a-97c7-faec71979e4b)
step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

### OUTPUT:
![5](https://github.com/user-attachments/assets/393daa7f-8038-4e5b-a5e5-61fc0dc4eb5b)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

### OUTPUT:
![6](https://github.com/user-attachments/assets/374161d1-8cd9-4bdd-b494-f57af92bf0fe)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

### OUTPUT:
![7](https://github.com/user-attachments/assets/13248041-b738-4472-b5b1-dafc456637fa)
The info command provides information regarding a module or platform,
![8](https://github.com/user-attachments/assets/792a0809-2759-490f-b516-95edc775592c)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:

### MYSQL ENUMERATION:
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![9](https://github.com/user-attachments/assets/cb6ef237-2f5b-4cea-bcee-0d91b4c8984e)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![10](https://github.com/user-attachments/assets/9c2ed021-733c-4b03-94a9-56978879ac5c)
use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![11](https://github.com/user-attachments/assets/c3e7fa5b-c278-478d-bb53-c777e60c5248)
Use the set rhosts command to set the parameter and run the module, as follows:
![12](https://github.com/user-attachments/assets/58a10ad3-ab9c-4e47-b9e2-c2b81e5ce39c)
 After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![13](https://github.com/user-attachments/assets/d209fee9-08a5-4749-8acd-81dec984269d)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists:

set PASS_FILE /usr/share/wordlists/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS

Set BLANK_PASSWORDS to true in case there is no password set for the root account.

set BLANK_PASSWORDS true
![14](https://github.com/user-attachments/assets/ed39c52f-ee96-4bc8-aa88-adce63df05f4)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
