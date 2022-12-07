## basic-mod2 (07/12/2022)
## Approach
Similar to basic-mod1, modified program to include a padding variable in characterSet and statement for calculating moddedValue
~~~
table = [104, 85, 69, 354, 344, 50, 149, 65, 187, 420, 77, 127, 385, 318, 133, 72, 206, 236, 206, 83, 342, 206, 370]
characterSet = "Xabcdefghijklmnopqrstuvwxyz0123456789_"
decryptedMessage = ""
for value in table:
    moddedValue = pow(value, -1, 41)
    decryptedMessage += characterSet[moddedValue]
print(decryptedMessage)
~~~
Output:
~~~
1nv3r53ly_h4rd_dadaacaa
~~~
Hence, flag is: picoCTF{1nv3r53ly_h4rd_dadaacaa}