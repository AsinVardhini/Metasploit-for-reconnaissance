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

## PROGRAM:
Find out the ip address of the attackers system.



## OUTPUT:
Invoke msfconsole:

![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/fb9ee731-6a06-4db2-bf87-8739851ad4da)




## OUTPUT:
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole:
![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/05321f33-8c8f-412c-b94f-c7301f6218de)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/23181869-34cf-42b6-b1a1-76dcac6baf07)

## OUTPUT:
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/86701abe-eea5-4c19-a0b4-ff7df4ac9168)

## OUTPUT:
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/5a78cefa-970f-49dc-a6aa-4820ac8ed704)

The info command provides information regarding a module or platform.
![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/e8c28c49-2758-4a17-9954-d67eb34f4f0c)

## OUTPUT:
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init
![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/31502b5b-9ff5-420a-a336-5b359b99f5bd)

## MYSQL ENUMERATION:
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan 
the MySQL database at 3306 port.

db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
## OUTPUT:
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/39be6a58-391d-4ca1-a5fa-a5af0b29a953)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/e3adae25-a5cb-4ee1-b44b-cd1320f37d5d)

Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/0d3354a4-6104-43a8-865a-b0fd519325dd)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/ec2fd0ef-e4f3-45e3-a85f-677c436a9ce3)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/00495dde-12aa-4df1-9a21-1dc5a6fcb270)

![image](https://github.com/AsinVardhini/Metasploit-for-reconnaissance/assets/119417735/08d83442-e2cd-41a9-a03a-d1edb24b5553)







## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
