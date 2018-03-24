# REV2
Challenge :
![](https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/rev_2/rev_2.png?raw=true)


Firstly to be aware of what strings in it I run strings command and check out the flaw. Found that:
![](https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/rev_2/rev2%20images/rev2_Strings.png?raw=true)
I see there are two levels of  reaching the flag out. In this case let go through:
yeah just like what hint said I went to radare2 and analyze the main function..

```
r2 -d ./rev2_32
[0xf7f79c70]> aaaa #analyze all file
[0xf7f79c70]> pdf@main
```
Here is first we need to look:
![](https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/rev_2/rev2%20images/rev2_radare_main_1.png?raw=true)

Now take attention over here that highlighted row:
```0x08048546      3dd7110000     cmp eax, 0x11d7
   0x0804854b      741e           je 0x804856b
```
Our first input get compared with 0x11d7. What that mean is in decimal system=  4567
If I do enter random one it'd take me through
```0x08048554      6834870408     push str.Sorry__your_guess_of__d_was_incorrect._Try_again
```
So I pass easily to second level. By that mean is we jump at 0x804856b.
and Level 2 question is asked as you can see in the image above.
We enter second input/S cuz just like in question it want 2 inputs from us and  
##A rule there is ! 
First input < Second Input. Ok so look what happe next ?
![]https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/rev_2/rev2%20images/level2_meet_reuirements.png?raw=true)
```Firstly both of our inputs get controlled if the both are in between 9<x<99 or not
```
Ok, lets take attention and right input after.
![]https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/rev_2/rev2%20images/rev2_radare2_level2_check.png?raw=true)

Now look carefully !:
```  
0x080485d4      8b55e8         mov edx, dword [local_18h]
|      ||   0x080485d7      8b45ec         mov eax, dword [local_14h]
|      ||   0x080485da      0fafc2         imul eax, edx
|      ||   0x080485dd      8945f0         mov dword [local_10h], eax
|      ||   0x080485e0      817df0670d00.  cmp dword [local_10h], 0xd67 ; [0xd67:4]=-1 ; 3431
|     ,===< 0x080485e7      741f           je 0x8048608
Our two inputs get multiplied if they are succesful input by the rule. Then get compared to  decimal '3431'
```
In this case i immediately check which ones are divisor of 3431:
sorry not quite well math I have, to solve this in ma mind :D 
![]https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/rev_2/rev2%20images/final_number.jpg?raw=true)

Flag:
```
Congrats, you passed Rev2! The flag is: actf{4567_47_73}
```





