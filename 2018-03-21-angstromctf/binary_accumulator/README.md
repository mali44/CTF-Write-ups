# Accumulator

![](https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/binary_accumulator/binary_accumulator.jpeg?raw=true)

Hints are very helpful in this ctf. So you will simply realize that program doesn't accept  over limited digits. 
We know its around 2,1 billion a int value can store. Further more integer can convert to negative number

```
An integer overflow can cause the value to wrap and become negative,
which violates the program's assumption and may lead to unexpected behavior 
(for example, 8-bit integer addition of 127 + 1 results in −128, a two's complement of 128).
```

So my sloution was:

![](https://github.com/mali44/CTF-Write-ups/blob/master/2018-03-21-angstromctf/binary_accumulator/accumulator.png?raw=true)

when you run it on server side :
Flag:
```
actf{signed_ints_aint_safe}
```

