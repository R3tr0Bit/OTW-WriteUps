***
# bandit_level5->6
***
<img width="864" height="237" alt="image" src="https://github.com/user-attachments/assets/b2ec7481-3aeb-468b-a55f-f6729ee9b853" />  

In this level, we have three particular properties that we need to follow in order to find the password:   
- human-readable  
- 1033 bytes in size  
- not executable  
  
Due to the fact that inside the **inhere** folder there are many subdirectories and files,  
<img width="905" height="120" alt="image" src="https://github.com/user-attachments/assets/88ae1073-81c4-48c0-a614-4016923dc08b" />  
we can use the `find` command to locate our file.  
<img width="852" height="153" alt="image" src="https://github.com/user-attachments/assets/025e90f4-50fd-4e8f-aee8-ba8ad87d1566" />  
Manually checking each folder one by one would be pretty time-consuming, and we definitely don’t want to do that.  

The solutions at this point are multiple.  

If we consider the properties above, the solution can be found just by using the size. In fact, if I put the option `-size` in `find` we get the file containing the password:  
<img width="463" height="97" alt="image" src="https://github.com/user-attachments/assets/390324ef-390c-432f-bc01-1f093f2a733f" />  

Ok — at this point we have two choices: either continue exploring the commands to learn more about their functionality, or simply `cat` the password and move on.  

Whatever you choose, let's start by following the first option.  

We want to try `find` with all the properties above:
- human-readable:  
This property cannot be fully checked using only `find`. Sure, we might identify some files that are regular files, but we cannot be certain if they are truly human-readable. So, let's go ahead with the other two properties
- 1033 bytes in size and not executable:   
These properties can be checked easily. In fact, if we look at the man page, there is an option that allows `find` to filter the search. We can add this option followed by `1033c` to narrow down our results.  
<img width="862" height="552" alt="image" src="https://github.com/user-attachments/assets/56e6035c-1b4f-4041-8756-3db6bd9e7543" />

Now that we know about the size option, we can check the non-executable property.  If we look at the man page, we find the   
`-executable` option, which allows us to locate files that are executable by the current user.  
<img width="858" height="206" alt="image" src="https://github.com/user-attachments/assets/a449bb8b-efbd-4e8e-b8a8-a442f62fc78a" />  

However, we need to find a **non-executable** file.  In this case, we can use the **!** symbol to negate an option. When placed before an option, it makes that option work in the opposite way.  
Here’s how the command can look:  
<img width="601" height="77" alt="image" src="https://github.com/user-attachments/assets/8a6a214a-1913-445f-b533-e523f95211d8" />  
The results it's the same as `find ./* -size 1033c`, but if we try to execute the command omitting the `-size` option, the results will be different and a lot more:  
<img width="344" height="899" alt="image" src="https://github.com/user-attachments/assets/8b11e2ab-8eb1-4931-a5e7-9c7bb27dfaf6" />  
Finally, we want to add the **human-readable** property to our command.  
We can use `file` to see if a file is an ASCII text or not (This helps us to know if it's a human readable file or not). 
<img width="776" height="83" alt="image" src="https://github.com/user-attachments/assets/ce597660-207e-49fb-986b-a61c25156e16" />  
<details>  
  <summary>Let's break down the command  </summary>
  
  >The command `find ./* -size 1033c ! -executable -exec file {} \;` might seem difficult to understand at first glance, but in the end, it's actually quite simple.
  >Let's say that the first part has already been well explained in the previous sections, while the second part still needs clarification.
  >- `-exec` - This first part tell to execute something
  >- `file` - This is the command that `-exec` will execute.
  >- `{}` - This part tells the command to execute `file` on each result from the first part (the one using `find`).
  >- `\;` - This is the stop of the command. Tells `exec` to stop and exit.
</details>

Now that we have our file we can `cat` the result!!

<img width="855" height="308" alt="image" src="https://github.com/user-attachments/assets/bee52cd9-73ea-4f6e-9ed9-8ae6da7b88aa" />  

Following the explanation above, we can use also a little "add-on" to cat all in one line:  

<img width="930" height="347" alt="image" src="https://github.com/user-attachments/assets/ee9d8683-269a-47e7-9564-6be69dfa2d66" />  

Here it goes!!  

















    



