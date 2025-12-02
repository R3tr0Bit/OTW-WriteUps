***
# bandit_level12->13
***  
<img width="1645" height="308" alt="immagine" src="https://github.com/user-attachments/assets/a310ed22-9ae5-4484-bfcb-10eb1e3800d9" />
  
In this level there will be a file compressed many times.  
What we have to do is understand which type of file it is and use the correct command each time.

The first step is to create a temporary directory where we can work using `mktemp -d`.
  
<img width="286" height="96" alt="immagine" src="https://github.com/user-attachments/assets/bf104206-f73e-4422-9875-3200715f1dfc" />  
  
This lets us work inside a temporary directory that, once we log off, will be destroyed along with all its content (or according to the system rules, if they differ).  
As you can see in the image below, I navigated into it, copied the file from the home directory, and inspected it by running `file`.
 
<img width="659" height="173" alt="immagine" src="https://github.com/user-attachments/assets/70fa7366-8f8f-4de0-bf0f-481cacbad97a" />   
  
Now that we know it is an ASCII text file, we can try to print it.  
  
<img width="681" height="765" alt="immagine" src="https://github.com/user-attachments/assets/4b9fdc0d-7785-4929-9112-fd58d61b8d80" />  
  
We can see that it's not a normal ASCII text file, but a HexDump file.  
Now we can work on it, trying to revert it to its previous state.  
From the screen below, we can guess that the previous file could be a **.bin** file, but to be sure, let's proceed and reverse it.
  
<img width="682" height="85" alt="immagine" src="https://github.com/user-attachments/assets/a4c5e783-ed66-436b-b641-adc0822b6075" />  



