***
# bandit_level4->5
***
<img width="1057" height="152" alt="image" src="https://github.com/user-attachments/assets/5ea35b8d-538a-4d56-828c-25b95ecf3489" />  
As stated in the level description, our goal is to find the password inside the only human-readable file. Note that the description says human-readable, not merely readable: this suggests the file is plain text (for example, ASCII) that can be read directly by a person, rather than a binary file that would require conversion from machine format to a human-readable form.  

Let's start by typing `ls` to see that we have a folder to explore:  
<img width="210" height="80" alt="image" src="https://github.com/user-attachments/assets/355fba74-61f7-44e3-98f4-3486cf171569" />  

Once inside the folder, typing `ls` again shows that we have multiple files to analyze  
(**Note** that these filenames start with a dash [**See Level 2**](https://github.com/Nanospaziale/OTW-WriteUps/blob/main/bandit/level02.md)).    

Let’s start by using `file`, a command that helps us determine what type a file is.

<img width="1021" height="227" alt="image" src="https://github.com/user-attachments/assets/b9ff68cd-469d-4668-88f3-165095c86982" />  

So, with `file`, we can use the command `file ./-*`.  

<img width="351" height="252" alt="image" src="https://github.com/user-attachments/assets/f6459747-f6a0-48c4-a93a-9a808c2085b9" />  
  
***  
  
<details>
  <summary>Here's the explanation of the command I used above:  </summary>
  
  - `file` - Simply the command
  - `./` - This is one of the method that we can use to open dashed file (Used also in level 2)
  - `-*` -  Explicitly tells `file` to open all files whose names start with a dash `-`, regardless of what comes after.
  >In simple terms, the `*` symbol is a wildcard used in the shell to represent “anything.”
  >That means it can stand for any number of characters in a filename or path. For example, `file*` matches `file1`, `file2`, or `fileX`.
  >So when we write `-*`, we’re telling the command to include all files whose names begin with a dash, no matter what follows.
</details>
  
***  
  
At this point, we can see that the only readable file among the others is -file07 (ASCII text).  
<img width="389" height="100" alt="image" src="https://github.com/user-attachments/assets/b2102572-f610-496c-aad9-156fc50d052a" />  
There it is — we’ve found the password for the next level!



