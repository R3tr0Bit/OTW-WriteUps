***
# bandit_level1->2
***
<img width="633" height="140" alt="image" src="https://github.com/user-attachments/assets/2b33fd08-a0d4-4f2c-a53f-c23a221b7510" />  

In this level, the password is stored in a file called - located in the home directory.  

Now that we are connected we can type `ls`  

<img width="146" height="46" alt="image" src="https://github.com/user-attachments/assets/b4f5d61a-ec0f-49f3-b026-f5d3a95d15c0" />  

Now we need to open the **-** file present in the home directory.  
As well as the previous level, there are a bunch of methods to open this file, but first let's analyze and understand what a dashed file is.  
A dashed file is one that starts its name with a **'-'** 

In this case, the only file present here in the directory is **-**.  

If we try to open it with most of the utilities used in the previous level, the screen will be hung because the standard [POSIX](https://en.wikipedia.org/wiki/POSIX) treats the **"-"** as standard input. Thus, most commands consider this file as Standard Input (StdIn) and not as a regular file.  
<img width="242" height="139" alt="image" src="https://github.com/user-attachments/assets/0a766a35-6ee9-47bd-9edd-e8366e1cbec7" />  

<img width="254" height="102" alt="image" src="https://github.com/user-attachments/assets/57c2aa8f-c2e9-457c-87f3-b55906ee6e47" />  

To use these commands and let them treat **"-"** like a file and not a StdIn, we need to use **./** or the **/full/path/to/the/file**.  
Let's try:  

<img width="329" height="61" alt="image" src="https://github.com/user-attachments/assets/ba482412-0a70-42b2-ae80-0c85faab6b72" />  


To see the full path of the file, we can use the command `pwd` in the directory where the file is  

<img width="219" height="62" alt="image" src="https://github.com/user-attachments/assets/9198e0ac-2204-413c-9096-9f504627fa79" />  


So the final command will be

<img width="380" height="58" alt="image" src="https://github.com/user-attachments/assets/ff605020-8a74-4db3-aadd-6c9f540c41fa" />    

Here we go, we have our password!!

***
**Note**  
In the previous level, I did not use the command `more`. In fact, if you use this command with the dashed file, you will notice that more prints the content of the file directly and does not treat - as standard input (StdIn).  
<img width="330" height="60" alt="image" src="https://github.com/user-attachments/assets/f63e1bf5-8396-43fa-9a3b-11aa3661b40c" />

Why?  
The explanation comes from the command's history.  
If we do some digging, we can see that `more -` treats **“-”** as a literal filename, not as stdin, so it tries to open a file named **“-”** and, if it doesn’t exist, just reads stdin by fallback and prints it immediately.
On the other hand, `less -` or any other commands quoted above , explicitly interprets **“-”** as standard input, waiting for data to arrive before displaying anything. 



