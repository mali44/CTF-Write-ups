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
   0x0804854b      741e           je 0x804856b```
Our first input get compared with 0x11d7. What that mean is in decimal system= ```4567```
If I do enter random one it'd take me through
```0x08048554      6834870408     push str.Sorry__your_guess_of__d_was_incorrect._Try_again```
So I pass easily to second level. By that mean is we jump at 0x804856b.
![](https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/rev_2/rev2%20images/rev2_radare_main_1.png?raw=true)



