# bloat.py (09/12/2022)
## Approach
Opening the file using vim shows a Python script

Upon first viewing, it appears the code is obfuscated with the key:

~~~
a = "!\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ" + \
    "[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~ "
~~~

So I'll start by decrypting the script starting with the arg133 function, adding a print command at line 24 (before the input call)

~~~
def arg232():
    print(a[71] + a[64] + a[79] + a[79] + a[88] + a[66] + a[71] + a[64] + a[77] + a[66] + a[68])
    return input(a[47] + a[75] + a[68] + a[64] + a[82] + a[68] + a[94] + a[68] + a[77] + a[83] + \
                 a[68] + a[81] + a[94] + a[66] + a[78] + a[81] + a[81] + a[68] + a[66] + a[83] + \
                 a[94] + a[79] + a[64] + a[82] + a[82] + a[86] + a[78] + a[81] + a[67] + a[94] + \
                 a[69] + a[78] + a[81] + a[94] + a[69] + a[75] + a[64] + a[70] + a[25] + a[94])
~~~

Output:
~~~
happychance
~~~


This appears to be the password for the flag, hence the flag is:  
picoCTF{d30bfu5c4710n_f7w_161a4f09}