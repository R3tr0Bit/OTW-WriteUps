***
# bandit_level0
***
Level 0 is not a proper level. We should consider it an introduction to understanding how to connect to a server online through an SSH ([Secure Shell](https://en.wikipedia.org/wiki/Secure_Shell)) tunnel.
<img width="1697" height="405" alt="image" src="https://github.com/user-attachments/assets/505b9ae9-08c4-4b35-b97e-20fc0ba04139" />

As we can see in the first image, we can use the man page for a command to understand its functionality and all the various options that the command can provide us.

Of course, we can use any search engine to explore videos and tutorials on how to use something 
>Note: The man page explore every functionality of a command, but in most cases, it is not the best way to understand how a command works

The tipical use of `ssh` is `ssh login_name@server_address`. If no port is specified, the SSH command, as standard, uses port 22/TCP.
Since level 0 needs us to connect through a specific port (2220) , we can check the man page to see if there’s an option for that.

<img width="1026" height="246" alt="image" src="https://github.com/user-attachments/assets/1ac47899-31e7-42fd-b8d8-1cdb8ee5eb22" />
<img width="950" height="62" alt="image" src="https://github.com/user-attachments/assets/e51e2dd6-43e5-48d5-9dce-2433d2b36063" />

As we can see in the images above, the **-p** option can be used to specify a port.

So, our final command, will be: `ssh bandit0@bandit.labs.overthewire.org -p 2220`
>The username and password for this level are mentioned in the introduction of level 0 on the site, and they are **bandit0** and **bandit0**.

Once logged, we should see an image like this:

<img width="568" height="1183" alt="image" src="https://github.com/user-attachments/assets/6e0d41fb-089f-464c-a83d-39a68dfc1f86" />

Now that we're connected, we can dive into the challenges across all the levels!
