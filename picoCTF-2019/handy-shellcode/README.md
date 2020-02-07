# Handy Shellcode

## Level Task
> This program executes any shellcode that you give it. Can you spawn a shell and use that to read the flag.txt? You can find the program in /problems/handy-shellcode_3_1a2e95a810eefe4a5994631812c0b8af on the shell server.

## Writeup

This challenge was the most difficult challenge I have done so far and this simply came down to my utter lack of experience in binary exploitation as a topic. But I'm really glad that I did it for this reason; to gain the experience and open a whole new world of security.

Firstly, I looked in the directory, to find three files in total. ```flag.txt``` being the unreadable flag, ```vuln``` being the vulnerable binary and ```vuln.c``` being the binary's source code.

From here, I read the source code of the vulnerable executable to using ```cat vuln.c```, which output this:

![Screenshot](https://i.imgur.com/UbYujN3.png)

As you can see, it uses the vulnerable ```gets()``` function which does not check to see if the size of the input is greater than the size of the buffer, which obviously can be explited.

Next, using python's ```pwntools``` library already installed on the shell, I simply grabbed some code to run a shell using ```pwn.shellcraft.linux.sh()```. This returned to me the assembly instructions for the code, and not the shell code.

![Screenshot](https://i.imgur.com/pQpSZ4V.png)

This, was useless on its own and had to be converted into a usable form. So, to do this I used 
```print(pwn.asm(pwn.shellcraft.linux.sh())))``` to return the usable shellcode version of the payload.

![Screenshot](https://i.imgur.com/cZhoSNV.png)

Now that I have a payload that the vulnerable program can execute, I now have to pass the payload to it. To do this, I created a single-line python command that will import pwn and run the previous command into the ```vuln``` file.

![Screenshot](https://i.imgur.com/fU4lKpO.png)

But as you can see, the shell doesn't stay open so that we can run the code in the new group. So, to keep the shell open and allow for code execution, I simply appended ``` ; cat``` to the end of the command before the pipe. Then, with the shell open, I was able to execute any command I like, including ```cat flag.txt``` to finally get the flag

![Screenshot](https://i.imgur.com/WIgFp9T.png)
