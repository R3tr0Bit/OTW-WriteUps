***
# bandit_level9->10
***
<img width="922" height="157" alt="image" src="https://github.com/user-attachments/assets/59c8e68d-4de2-40b4-9bb4-56fa55a68e24" />  

Here we go with our file ***data.txt***.  
As usual, we can check the effective presence of the file through `ls`.  
<img width="211" height="78" alt="image" src="https://github.com/user-attachments/assets/9784ce81-39b4-4524-a2f9-fa75f1400338" />  
  
Once again, we use `file` to check what type of file we’re dealing with.  
<img width="319" height="98" alt="image" src="https://github.com/user-attachments/assets/d9006258-b88d-4b7e-acb7-46a688d4ba96" />  
  
Since our file is a *data* type, it means it isn’t human-readable.  
We can still print it to the screen, of course, but it will just show a bunch of unreadable characters.  

What we can do at this point is print to the screen every single readable lines with `strings` and then pipe `grep` to match only the line with several *"="*.  
Since we don't know how many of *"="* are in the line, i'm going to put 6 of them.  

Bingo, we got our password!  
  
<img width="498" height="156" alt="image" src="https://github.com/user-attachments/assets/e28958cf-b661-4253-b8a0-79287d8270e3" />  














