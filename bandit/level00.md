
***
# bandit_level0->1
***
<img width="1681" height="172" alt="image" src="https://github.com/user-attachments/assets/a9ed53a7-1212-4948-951c-afdda055992a" />  


This level tells us that the password is located in the home directory inside a file called "readme." By typing the command `ls`, we can print a list of files stored in the current directory. 
>The `pwd` command (Print Working Directory) can help us find out where we are.

<img width="163" height="48" alt="image" src="https://github.com/user-attachments/assets/998d724d-12e9-45f0-b734-a9edd7c0ff28" />


Now we can print directly the content of the file, but if we want to be sure that the file listed a moment ago is a readable file, we can check with the command `file`

<img width="211" height="47" alt="image" src="https://github.com/user-attachments/assets/04c31232-89df-442c-8584-00554daa4a75" />

As we can see, the command `file` helps us determine the file type. Since the file type is [ASCII](https://en.wikipedia.org/wiki/ASCII) we can print to the screen it's content.
There is a bunch of commans that we can use for print the content of a file, here are some:

`cat` it's the most common command to print the content of a file.  
<img width="588" height="146" alt="image" src="https://github.com/user-attachments/assets/6e1b0004-c1e2-4172-8b06-7e8d314ea92d" />

`tail` print the last 10 lines of a file.  
<img width="586" height="146" alt="image" src="https://github.com/user-attachments/assets/e2482cd5-a930-4394-a15c-27baad9483c8" />

`head`, do the opposite of `tail` by printing the first 10 lines of the file.  
<img width="586" height="143" alt="image" src="https://github.com/user-attachments/assets/87f0202e-f828-45f2-8e3d-1314a5334e72" />

`more` is an interactive command to explore the file. It will go in interactive mode, only if the screen size is not enough to print its content. Instead, if the screen size it is enough, it print and quit.  
<img width="592" height="148" alt="image" src="https://github.com/user-attachments/assets/77831840-1102-4026-9b9d-4a00db9b60ed" />

`less` is a better version of `more`, because it enter interactive mode, regardless of whether the screen size is sufficient.  
<img width="591" height="132" alt="image" src="https://github.com/user-attachments/assets/7f235f10-3b38-48a8-888a-d4c401a8a23f" />  

As we can see, there are a bunch of methods to see the content of a file!  
Now we have the password for level 2.

