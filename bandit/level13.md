***
# bandit_level13->14
*** 
<img width="1653" height="354" alt="immagine" src="https://github.com/user-attachments/assets/52f30728-da2e-45c6-a12b-47c9148c3ad7" />

In this level, running `ls` shows a file named **sshkey.private**:

<img width="219" height="80" alt="image" src="https://github.com/user-attachments/assets/a6fedebf-07e5-4ba1-87e5-465698996557" />

<details>
  <summary>What is an SSH key?</summary>

> When working with SSH, you’ll often come across SSH keys.  
> These are cryptographic keys that let you log into a server without typing a password.  
> For this to work, the server must have the **public** part of your key installed and configured to allow your user to log in.  
> Once that's done, you can authenticate using the **private** key, instead of a password.  
>
> If you want to explore the topic more deeply, look up tutorials or documentation online there’s plenty of good material out there.
</details>

Basically, this private key allows us to log directly into the server.

<img width="655" height="535" alt="image" src="https://github.com/user-attachments/assets/d4dace9a-4434-44a4-998e-404740094a31" />

The first thing to do is create a file on our local machine and paste the private key we obtained earlier.  
As you can see in the image below, I created a file and stored the SSH key inside it (exactly as shown previously on the server):

<img width="656" height="629" alt="image" src="https://github.com/user-attachments/assets/e9e0c7fd-b665-4335-84ca-8c50e8b6b206" />

Now, checking the `ssh` manual, we know that we can use this file to log into **bandit14** and retrieve the password.  
Using the following command, we can connect to the server:

`ssh bandit14@bandit.labs.overthewire.org -p 2220 -i sshkey.private`

<details>
  <summary> *** Note *** </summary>

> - The filename of the key can be anything you want, but using a meaningful name makes things easier.  
> - I had to log out from bandit13 and create the file locally because you cannot SSH into another server **from inside** bandit13 because this is restricted by the server's rules.  
> - Also keep in mind that the **private** key on your machine must have permissions set to `600`, while the **public** key should be `644`.
</details>

Now, using the command above, we can connect to bandit14.  
Once inside, we can print the content of ***/etc/bandit_pass/bandit14***:

<img width="487" height="79" alt="image" src="https://github.com/user-attachments/assets/06b5d910-f5f5-445c-a09d-b531042a25e0" />

And here we go, we have the password for the next level!


















