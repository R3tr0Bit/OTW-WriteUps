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

<details>
  <summary> Deepen the Hexdump files </summary>
  
> Hexadecimal is a base-16 numbering system.
> It uses 16 distinct symbols: 0-9 to represent values zero to nine, and A-F to represent values ten to fifteen.
> Hexadecimal is commonly used in computing because it provides a more compact and human - readable way to represent binary data compared to binary itself.
> I took this definition from https://linuxvox.com/blog/hexdump-linux/ - which i suggest to understand what a hexdump is and how it works.
</details>

From the screen below, we can guess that the previous file could be a **.bin** file, but to be sure, let's proceed and reverse it.
  
<img width="682" height="85" alt="immagine" src="https://github.com/user-attachments/assets/a4c5e783-ed66-436b-b641-adc0822b6075" />  
  
To revert a hexdump, we can use the command `xxd -r filename`.

In the screenshot below, you can see that the command prints the entire output (from the previous file) to the standard output. This isn’t ideal, because it makes it harder to work with.

<img width="1043" height="155" alt="image" src="https://github.com/user-attachments/assets/6263ed9c-b216-48d2-bdf7-33c97c64edfc" />

So what we can do instead is redirect the output of the command to a file.  
In this example, I redirected the output to *first_file*.

If we run `file` on it, we can see that our earlier guess was only partially correct.  
The name includes a **.bin** extension, but the actual format is ***gzip compressed data***.

<img width="1046" height="211" alt="image" src="https://github.com/user-attachments/assets/52e5c6db-feab-4976-9bd4-2c16f697677f" />

Since the `gzip` command can only extract *.gz* files, we need to rename *first_file* to *first_file.gz* using `mv`.

<img width="648" height="135" alt="immagine" src="https://github.com/user-attachments/assets/d595ff11-24a5-4924-8ef3-28a49325e6e9" />

Once we've renamed it with `mv`, we can use `gzip -d` to extract the file, and then run `file` again to check what kind of file we’re dealing with now.

We'll need to repeat this process for all the level:

  - Use `file` to figure out the file type  
  - Rename the file by adding the correct extension relative to the file type
  - Extract it using the appropriate command  
  - Go back to step one  

It’s a bit repetitive, but as mentioned in the description, this file has been compressed multiple times, so this is basically what we have to do.


<img width="590" height="229" alt="immagine" src="https://github.com/user-attachments/assets/43c1571b-58c0-4e59-a1cb-ccb05ef8a78e" />

<img width="663" height="135" alt="immagine" src="https://github.com/user-attachments/assets/7a974b30-2fd1-4216-ab72-1e4ea21e2c87" />

<img width="1045" height="174" alt="immagine" src="https://github.com/user-attachments/assets/215c94f9-bf83-47cd-902e-1e9fd8432e22" />

<img width="650" height="99" alt="immagine" src="https://github.com/user-attachments/assets/2be0958e-3da1-494b-9f1a-dc297c8bc0c9" />

<img width="587" height="172" alt="immagine" src="https://github.com/user-attachments/assets/aa80280a-7b00-4f44-b447-ae27cdce8c83" />

<img width="659" height="135" alt="immagine" src="https://github.com/user-attachments/assets/7070c011-011a-4201-8af0-dd1ed7097bc1" />

<img width="604" height="99" alt="immagine" src="https://github.com/user-attachments/assets/7926b188-e6d3-4dfb-a36f-ddf80b372f6c" />

<img width="666" height="173" alt="immagine" src="https://github.com/user-attachments/assets/d1a4160c-e52a-4d9b-b473-41450a7e2860" />

<img width="606" height="97" alt="immagine" src="https://github.com/user-attachments/assets/37b59fbd-0428-40e5-8dda-161d597a5a86" />

<img width="529" height="79" alt="immagine" src="https://github.com/user-attachments/assets/46c50156-4c9b-4916-b5f5-1fe8b8fdf4b5" />

<img width="653" height="115" alt="immagine" src="https://github.com/user-attachments/assets/7e68a853-54fc-4ca2-a246-2c072811966b" />

<img width="609" height="98" alt="immagine" src="https://github.com/user-attachments/assets/d6be3a54-5086-4363-ab77-a1b8dc5e356f" />

<img width="662" height="174" alt="immagine" src="https://github.com/user-attachments/assets/c58705b1-50a3-466f-81c9-18c4bcb67690" />

<img width="689" height="97" alt="immagine" src="https://github.com/user-attachments/assets/fb0f1bf9-0bb8-4ee7-b12c-2d5925259d25" />

<img width="1045" height="97" alt="immagine" src="https://github.com/user-attachments/assets/3e84519e-cfcd-4696-b151-088ea8048cba" />

<img width="739" height="117" alt="immagine" src="https://github.com/user-attachments/assets/1667d4b9-01ab-49a2-987d-b65c7d83fd3a" />

<img width="713" height="97" alt="immagine" src="https://github.com/user-attachments/assets/0c87f6d7-57fc-4d1f-8db4-cc79bb012c57" />

<img width="539" height="134" alt="immagine" src="https://github.com/user-attachments/assets/ad17d5dd-87d5-49c0-8a2c-96091ac302dc" />















































