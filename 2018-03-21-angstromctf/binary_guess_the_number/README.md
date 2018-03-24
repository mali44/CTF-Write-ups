# Guess the number

Challenge:

![](https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/binary_guess_the_number/binary_guess_number.jpeg?raw=true)

## Format String Vulns..

I tried to make some changes and look for stack value with %p I can see the values that I changed at the adress. Great so:
![](https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/binary_guess_the_number/guessthenumber.png?raw=true)

went off to server and tried to see what decimal numbers  in it ?
Look at what I found :))
First empty attemtion was to see if the sum of the rand numbers is arounde here or not. Yea there it is and second attemption for this helped us to see the real value which is addition of the values at 3rd address and 9th adress..


![](https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/binary_guess_the_number/guessthenumberFlag.png?raw=true)

Flag:

```
actf{format_stringz_are_pre77y_sc4ry}
```
