# basic-mod1 (07/12/2022)
## Approach
Pretty straightforward, just follow the instructions, wrote program in Python
~~~
table = [91, 322, 57, 124, 40, 406, 272, 147, 239, 285, 353, 272, 77, 110, 296, 262, 299, 323, 255, 337, 150, 102]
characterSet = "abcdefghijklmnopqrstuvwxyz0123456789_"
decryptedMessage = ""
for value in table:
    moddedValue = value % 37
    decryptedMessage += characterSet[moddedValue]
print(decryptedMessage)
~~~
Output:
~~~
r0und_n_r0und_add17ec2
~~~
Hence, flag is: picoCTF{r0und_n_r0und_add17ec2}
