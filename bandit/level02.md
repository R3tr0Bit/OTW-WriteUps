***
# bandit_level2->3
***
<img width="853" height="156" alt="image" src="https://github.com/user-attachments/assets/5253d4e6-c415-4d74-b2a9-eb615dc6f2c4" />  
  
This level asks us to find the password in a file called --spaces in this filename-- located in the home directory.  
Now, once connected we can print the content of the current directory by typing `ls`  
  
<img width="290" height="100" alt="image" src="https://github.com/user-attachments/assets/96d0ae88-3beb-4570-8e07-ce091e41db32" />  
  
We can see a file named `--spaces in this filename--` that begins with two hyphens, so we need to handle it the same way we handled the file in the previous level.  

At this point, using `cat --spaces in this filename--` isn’t correct. As we can see below, `cat` interprets the initial `--` as an option, which isn’t what we want.   
<img width="551" height="79" alt="image" src="https://github.com/user-attachments/assets/c99d70d7-2d6d-4016-aa50-bad8c5222914" />  

It’s important to note that throughout our journey on Linux, the `TAB` key should be our best friend. It represents auto-completion on a Linux machine and (particularly in this case) will be useful for completing filenames without having to type them letter by letter, including spaces or special characters that are hard to type for any reason.  

Now, wth the help of `TAB` and `./` we can print the file's content and finally retrieve our password:  
<img width="551" height="76" alt="image" src="https://github.com/user-attachments/assets/d6a29a02-8084-4edf-9ce7-a109024c64d7" />  
<img width="560" height="79" alt="image" src="https://github.com/user-attachments/assets/2b3b6574-0ea6-45df-9c96-39430a5eca19" />  
In this case, even `more` requires the use of `./`. This is because the file name isn’t just a single hyphen but includes other letters after the two hyphens, which causes the command to interpret them as an option (see below).
<img width="552" height="79" alt="image" src="https://github.com/user-attachments/assets/8ab19515-eca4-4884-89ef-840914b23249" />  

Of course, I haven’t mentioned them, but in the same way I used `cat`, it is possible to use other commands like `tail`, `less`, `head`, or any command that allows you to display a file's contents on the screen.  






