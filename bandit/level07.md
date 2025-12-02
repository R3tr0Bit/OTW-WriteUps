***
# bandit_level7->8
***
<img width="606" height="259" alt="image" src="https://github.com/user-attachments/assets/77ad1d8d-bf46-40a0-ad10-3fa6397d9ce5" />  
  
In this level we have to search the password in the file data.txt next to the word millionth.  
  
<img width="307" height="82" alt="image" src="https://github.com/user-attachments/assets/47e6fb84-c1bf-4571-ba60-9974c4c99a67" />  
  
`ls` will print to the screen our file *data.txt*.  

Before outputting the content, let's inspect the file size and line count.  
This can help us to know if we can simply cat the file or not (If inside *data.txt* there are 10 lines we can check it manually).  
To do so, we can use `wc -l filename`. This will print to the screen the line count of data.txt.  
  
<img width="337" height="79" alt="image" src="https://github.com/user-attachments/assets/88758637-a3f6-4aaa-bc9a-ed54717f3d82" />  

Or we can use `nl filename`, however, the difference from the previous command is that `nl` also prints the line content along with its line number.  
  
<img width="612" height="673" alt="image" src="https://github.com/user-attachments/assets/c636c259-af04-4814-9a93-9bdedc2ef38c" />
  
We can agree that 98567 lines are a bit too much to be read one by one. (However, if you are a patient person, you can read one by one!!)  
At this point, we need to tell to the pc that we want only the line that contains the word *millionth*.  
  
`grep` comes in handy with this type of problem. In fact, this command filters lines that match a given pattern.  
  
We can pipe `grep` to every single command that prints the content of a file to the screen, e.g. `more`, `less`.  
Be careful when using `head` and `tail`, as the command might fail to find the word *millionth* if it’s not within the first or last 10 lines of the code.  
Of course, you need to pass the option -n to `tail` or `head` or they will check only the first and last 10 lines of the file.  

Let's see some commands then:  

- cat
<img width="523" height="99" alt="image" src="https://github.com/user-attachments/assets/989a45c2-b70f-4299-a08b-cf651a95e71d" />
  
- more  
<img width="500" height="79" alt="image" src="https://github.com/user-attachments/assets/e083cad7-c322-442f-9f57-c33ed3bc0b2d" />  
  
- less  
<img width="496" height="78" alt="image" src="https://github.com/user-attachments/assets/9fcfd1f8-f77f-4922-a8c9-cf0895f11e37" />  
  
- head  
<img width="590" height="80" alt="image" src="https://github.com/user-attachments/assets/b805ae9a-1eda-4a4e-bfb1-873ff14eeb3d" />  
  
- tail  
<img width="583" height="76" alt="image" src="https://github.com/user-attachments/assets/43860552-2f41-4cfe-b5ae-4751ebc6b233" />

- nl
<img width="577" height="78" alt="image" src="https://github.com/user-attachments/assets/b220afea-f67b-404f-8f62-cf1717571d7d" />
  
***  
  
<details>
<summary> Case insensitive search </summary>

> The command `grep` is case sensitive, so be aware of what you type in the command!! However there are various options for this command, like `-i`
> <img width="970" height="77" alt="image" src="https://github.com/user-attachments/assets/b516f3a8-bcb3-475d-b43c-41cffa1892c6" />
</details>
  
***  
  
Let’s go ahead now that we have the password!


















