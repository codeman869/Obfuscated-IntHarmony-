# Obfuscated-IntHarmony-
**Description**


An obfuscated Ruby implementation of a coding problem proposed in /r/dailyprogrammer (http://redd.it/32goj8). This is a function which takes two 32 bit integers and compares their binary values to measure how compatible they are. This program uses simple logic to determine this. 

**Example**

If we were to compare two 8 bit integers, for example 1 & 2, we see that:

Number | Binary
--------|--------
1 | 0000 0001
2 | 0000 0010

As we can see, these numbers have 6 bits in common, or they are 6 / 8 * 100 = 75 percent compatible.

The conditions to match must satisify these requirements

Bit from 1<sup>st</sup> number | Bit from 2<sup>nd</sup> number | Output
-------- | -------- | --------
1 | 1 | True
1 | 0 | False
0 | 1 | False
0 | 0 | False

The logic used to accomplish this was *! (p ^ q)*

**Starting Point**

Below is the original code starting point, and used a little more complex logic:

```Ruby
def intHarmony(a,b)
    c = ("1"*32).to_i(2)
    d = (a & b) | ((c-a)&(c-b))
    puts "%d%" % (d.to_s(2).scan(/1/).size*3.125) + " Compatibility"
    puts "#{a} should avoid #{c - a}"
    puts "#{b} should avoid #{c - b}"
end
```
