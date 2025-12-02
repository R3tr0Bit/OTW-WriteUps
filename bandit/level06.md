***
# bandit_level6->7
***
<img width="733" height="234" alt="image" src="https://github.com/user-attachments/assets/0271756d-6352-44f5-99b6-905675f57372" />  
  
This level is very similar to the previous one, except for the proprerties of the file we are searching for.    
- Owned by user bandit7  
- Owned by group bandit6  
- 33 bytes in size  

If we try running `ls`, we can see that there are no files or directories.  
Indeed, as mentioned in the level description, we need to search for the file across the entire server.  
<img width="211" height="60" alt="image" src="https://github.com/user-attachments/assets/eb108f4d-62dd-4cc1-b825-109cef99266f" />  

In this particular case, we have to search in the root folder **/** (Root directory by default in most unix system, but it can be changed. [Unix filesystem](https://en.wikipedia.org/wiki/Unix_filesystem)).

We can use `find` again, but in this case we need to change some options.
If we look through the man page of `find` we can see that to search for our file we can use 2 particular oprions:
- **group gname** - In this case gname is bandit6 (gname stands for group-name)  
<img width="652" height="63" alt="image" src="https://github.com/user-attachments/assets/aa629f4a-023f-449c-a84c-8a29b3a953a2" />  

- **user uname** - In this case uname is bandit7 (uname stands for user-name)  
<img width="625" height="68" alt="image" src="https://github.com/user-attachments/assets/675bb342-fc68-4360-bec8-920253254aab" />

Now, the final command would be: `find / -size 33c -group bandit6 -user bandit7`  
<img width="600" height="1349" alt="image" src="https://github.com/user-attachments/assets/fcf32e85-5d9e-45e2-b5b7-dba2ae57138a" />

This is the output of the command.  
I shortened it because it produced a lot of errors, typically many “Permission denied” messages, since there are evidently quite a few files with the same properties as our target file.  

What we can do now, it's to redirect all the errors to /dev/null.  
In our case, redirecting the StdErr (2) to /dev/null, allow us to prevent all errors to be printed to the screen, letting us to see more clearly the file we need.  
You can imagine **/dev/null** as a bin or a black hole. Whatever you redirect to /dev/null disappear.  
  
***  
  
<details>
<summary>!! Check this out !!</summary>  

>More infos about Standard Stream can be looked up here: [Standard Stream](https://en.wikipedia.org/wiki/Standard_streams)  
>More infos about /dev/null can be looked up here: [/dev/null](https://en.wikipedia.org/wiki/Null_device)
</details>
  
***  
  
Doing `find / -size 33c -group bandit6 -user bandit7 2>/dev/null` results in:  
<img width="757" height="99" alt="image" src="https://github.com/user-attachments/assets/bdc5c60a-83d9-4cab-a331-f39b5f8d93e8" />  

As we can see, all the errors no longer appear on the screen, and the only file we can open is right there, ready to be read.  
<img width="581" height="80" alt="image" src="https://github.com/user-attachments/assets/e685018b-c071-4ec7-a329-98af17159b0f" />  

As well as for the other levels, we can integrate `cat` inside the command:  
<img width="919" height="80" alt="image" src="https://github.com/user-attachments/assets/94231a51-473e-4c87-9aee-1212247287c7" />  

Or we can pass the entire previous command as a parameter to `cat`, like this:  
`cat "$find / -size 33c -group bandit6 -user bandit7 2>/dev/null"`.  
With this method, `cat` prints the content of the file found by the command above.  
<img width="854" height="80" alt="image" src="https://github.com/user-attachments/assets/17bf3857-c997-43af-8863-392536beaa4a" />  

Here we goes with our password!






















