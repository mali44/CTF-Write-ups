# REV_1
![](https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/rev_1/rev_1.png?raw=true)

I listen to hint and run `strings` command.
Cuz if you run the file you are asked for correct password.
when we run the strings command to find out the strings in the rev1_file:
Came across with those:
```bash
s3cret_pa55word
Sorry, the password isn't %s. Try again!
Correct! You read my mind, have a flag: 
/bin/cat flag

```
Enter s3cret_pa55word in server side  and get the flag :

```
actf{r3v_is_just_gettin_started!}
```
 
