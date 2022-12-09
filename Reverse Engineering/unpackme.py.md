# unpackme.py (09/12/2022)
## Approach
Upon first viewing, it appears the program is encoded within plain
Thus since we have excess to the program we can do a print to see whats being executed

~~~
import base64
from cryptography.fernet import Fernet

payload = b'gAAAAABiMD06eCisTWoohiYL5jHGdCte5LAviTFguZQSIyRLAWICJpmdrgxhdTB923h6eksddKpKH41I5-HGzI6xGF_7eb_1u0S2Phw2NvYGTF1KzE1-AU66FfIW6QXWnCpPHOS9CatNBuFXuyjEAx86Rld2E7GjvuKEOJJXx_GZE2JgAxnDmvcewoksfjVCCAwNqzixpUPKkIET2xmO4EsDqK4CUG8_JxP0HwSEzW4PH-hVpZrkyse4EodFPsjs7NVJF0hL1_8bP1TCiEEnFn7hCoTRRvlpYQ=='

key_str = 'correctstaplecorrectstaplecorrec'
key_base64 = base64.b64encode(key_str.encode())
f = Fernet(key_base64)
plain = f.decrypt(payload)
print(plain) # Show program
exec(plain.decode())
~~~

Output:
~~~
b"\npw = input('What\\'s the password? ')\n\nif pw == 'batteryhorse':\n  print('picoCTF{175_chr157m45_cd82f94c}')\nelse:\n  print('That password is incorrect.')\n\n"
What's the password? 
~~~

Hence the flag is:  
picoCTF{175_chr157m45_cd82f94c}