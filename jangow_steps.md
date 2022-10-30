# Jangow 192.168.56.101
## Andrea Zonnekus 18758119

First find the hosts; do this with netdiscover and nmap and compare

Get my own ip: 

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.001.png)

sudo nmap -p 20  192.168.56.101/24 –exclude 192.168.56.101

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.002.png)

sudo netdiscover -i eth0 -P

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.003.png)

Ignore the network address, 192.168.56.100 and 192.168.56.118 are open

Find information on the services running

sudo nmap –vv -F -sV –version-light -O –osscan-limit 192.168.56.100 192.168.56.118 -oN Documents/jang/initial\_scan

-Running a *fast* scan which does some light investigation into what services and operating systems are running with a verbose and file output

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.004.png)

Can see none of the ports on the first host are listening

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.005.png)

Second host interesting, Apache web service running on 80 and ftp on 21

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.006.png)

Lets try the easiest option first


Get any useful pages on the server

sudo dirb http://192.168.56.118:80 /usr/share/dirb/wordlists/vulns/apache.txt -wSi -o useful\_pages

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.007.png)

There is a file with the server status, but nothing we can really use since we get 403 Forbidden



Get hidden files

sudo nikto -host http://192.168.56.118:80 -output hidden\_pages.csv

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.008.png)

Checked the README



Check the ftp service

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.009.png)

Nothing useful

Redo this with XML output because it helps Searchsploit

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.010.png)



Check searchsploit

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.011.png)

Probably not applicable

Use some password lists and common usernames to try and find the ftp login

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.012.png)



While waiting, check the webserver again

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.013.png)

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.014.png)

Interesting



We have a username

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.015.png)

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.016.png)

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.017.png)

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.018.png)

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.019.png)



Get some system information

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.020.png)

Mmm seems standard

Start another brute force attack

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.021.png)

Try and get more host information

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.022.png)



More

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.023.png)

After searching for Linux 3 and Linux 4, this module looks interesting:

<https://www.exploit-db.com/exploits/40503>

Make a shell with msfvenom

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.024.png)

Do some things but my shells refuse to stick – 

Try another type of shell

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.025.png)

Use python to spawn a proper shell

Get OS information from inside

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.026.png)

<https://www.exploit-db.com/exploits/47163>

Get a reverse shell in metasploit and get the exploit

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.027.png)

Didn’t work, tried a bunch of other exploits for the kernel

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.028.png)



<https://www.exploit-db.com/exploits/45010>

This could be it

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.029.png)


![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.030.png)

Looks promising

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.031.png)

I’m in!

![](jangow_steps/Aspose.Words.84446b37-ba5d-4f1d-8c28-f05b6e1a0584.032.png)

Finally – and without using dirtycow
