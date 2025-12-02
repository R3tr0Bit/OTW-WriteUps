***
# bandit_level8->9
***
<img width="752" height="245" alt="image" src="https://github.com/user-attachments/assets/c7d463ba-e68e-42dd-98b4-d7a5589479e7" />  
  
This level tells us that the password is the only line that appears once in the file **data.txt**.  
After confirming the file’s presence with `ls`, we can start working on it.    
  
<img width="211" height="80" alt="image" src="https://github.com/user-attachments/assets/45708255-823b-4562-ad4f-924e2d7187cb" />  
  
Here we go.  
First, we need to run `file` to see what kind of file it is. It turns out to be an ASCII text file, so we can go ahead and check how many lines it has.  
  
<img width="322" height="79" alt="image" src="https://github.com/user-attachments/assets/7e3b700e-c0e4-46eb-9c62-1c8828cf0f94" />  

Using the `wc -l` command, we can see that the file has 1001 lines, too many to check one by one.  
<img width="333" height="78" alt="image" src="https://github.com/user-attachments/assets/8cee01ee-cae0-4d2c-b1b3-3b7aee33d2d1" />  
  
At this point, we can concatenate various command to get our password:  
With command `cat data.txt | sort | uniq -u` we can retrieve easily our password from the file ***data.txt***.  
<img width="482" height="96" alt="image" src="https://github.com/user-attachments/assets/b1b3b450-74b5-4eb7-bad8-78b53548952c" />  
  
***  
  
<details>
  <summary> Why use sort? </summary>
  
> Since I'm a curious person, I always try to understand *why* a command works the way it does.  
> In this particular case, why do I need to use `sort | uniq -u` instead of just `uniq -u`?  
> If I try `cat data.txt | uniq -u`, I get a completely different result from the one obtained with `sort`. But why?  
> 
> <img width="412" height="382" alt="image" src="https://github.com/user-attachments/assets/b24a4cb7-1a5f-4df9-91eb-c982ef89fedd" />  
> 
> According to the manual, the `-u` option should print only the lines that occur once.  
> But how does it actually determine whether a line appears only once?  
> After doing some research, I found that `uniq -u` does not print lines that occur only once globally, but lines that occur once **consecutively**. What does that mean?  
>
> <img width="492" height="233" alt="image" src="https://github.com/user-attachments/assets/2561a775-f324-4c69-b5b5-4ea1595ea040" />  
>
> As you can see in the image above, if I try to print 3 words and pipe `echo` into `uniq -u`, the result is not what I expected.  
> This command prints the words that repeat **consecutively**, not the ones that occur only once.  
> Instead, using `sort` before `uniq -u` returns the words that actually occur only once.
> So, `uniq -u` only considers consecutive lines. If a line appears multiple times non-consecutively, it’s treated as unique relative to the previous line.
</details>
  
***  
  
That's it, we got our password!










