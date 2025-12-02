***
# bandit_level3->4
***
<img width="555" height="255" alt="image" src="https://github.com/user-attachments/assets/3a152ad7-da06-4b78-bdc0-b5853e010d9c" />   
  
Following the description above, we can see that our password is stored inside a hidden file in the directory `inhere`.  
  
Once logged in, we can easily find the folder mentioned in the description by typing `ls`.  

<img width="297" height="78" alt="image" src="https://github.com/user-attachments/assets/6157ee69-2bc9-4ea4-808d-ce75836bc934" />  

We can dive into this folder, but unfortunately, there won't be any files — or at least, that’s how it looks at first.  

<img width="294" height="120" alt="image" src="https://github.com/user-attachments/assets/15f33091-e7dd-42a4-93a8-bbadaa28cd71" />  

In fact, as stated in the level’s description, the file we’re looking for is hidden.  

By browsing through the man page of `ls`, we can find some interesting options.  

`-a`  
  
<img width="471" height="71" alt="image" src="https://github.com/user-attachments/assets/e7dcce38-4dfd-4175-9a2d-5a080997dbf3" />  

Bingo!  
Using `ls -a` our file will be shown and we can use our typical command to open it.  

<img width="315" height="77" alt="image" src="https://github.com/user-attachments/assets/e4c9a5b3-d6a4-42ee-b940-5ec843f70be4" />  

Using `cat`, but we can use also the other commands from the previous level.  

<img width="481" height="79" alt="image" src="https://github.com/user-attachments/assets/2328738a-1c42-44cd-b93a-a363896f5fdb" />  
  
    
> TIPS: While using `ls`, I recommend using these options: `-a` (to show all content), `-l` (to display the output in long list format), and `-h` (to show file sizes in a human-readable format).  
> The first two options (`-l` and `-a`) can also be used by running the command `ll` (on most modern filesystems).  

