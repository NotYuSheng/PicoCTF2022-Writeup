# credstuff (08/12/2022)
## Approach
Found the equivalent password for specified username using a Python script
~~~
def main():
    index = 0
    f = open("usernames.txt", "r")
    for line in f:
        line = line[:-1]  # remove newline
        if line == "cultiris":
            targetIndex = index
            break
        index += 1

    f = open("passwords.txt", "r")
    index = 0
    for line in f:
        line = line[:-1]  # remove newline
        if index == targetIndex:
            print(line)
            break
        index += 1


if __name__ == '__main__':
    main()
~~~
Output:
~~~
cvpbPGS{P7e1S_54I35_71Z3}
~~~

The flag seems to be encrypted by key mapping. Judging by the format, I've made some assumptions: 
* Special characters unchanged
* Case unchanged
* Numbers are unchanged
* Mapping is one to one

We know that we the flag should be in this format: picoCTF{xxxxxx}  
Hence we can map the output and get some of the key mappings  

c = p  
v = i  
p = c  
b = o  
P = C  
G = T  
S = F  

Eliminating duplicates and reducing to lowercase:  
c = p  
v = i  
b = o  
g = t  
s = f  

A quick look at the difference between the characters shows something interesting:
~~~
def main():
    print(abs(ord("c") - ord("p")))
    print(abs(ord("v") - ord("i")))
    print(abs(ord("b") - ord("o")))
    print(abs(ord("g") - ord("t")))
    print(abs(ord("s") - ord("f")))


if __name__ == '__main__':
    main()
~~~

Output:
~~~
13
13
13
13
13
~~~

Which probably means the passwords are encrypted using ROT13  
Hence the flag is:  
picoCTF{C7r1F_54V35_71M3}
