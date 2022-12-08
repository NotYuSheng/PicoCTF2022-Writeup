# file-run1 (08/12/2022)
## Approach
Opening the file using vim shows an ELF header

Some notable commands to interact with elf files are:  
* elfedit
* objdump
* hexdump

Using the following command, we can display the source code with disassembly:
~~~
objdump -s run
~~~

And we can find the flag within the output:
~~~
Contents of section .rodata:
 2000 01000200 00000000 7069636f 4354467b  ........picoCTF{
 2010 5535314e 365f5930 55725f46 31723537  U51N6_Y0Ur_F1r57
 2020 5f463131 335f6535 35353964 34367d00  _F113_e5559d46}.
 2030 54686520 666c6167 2069733a 20257300  The flag is: %s.
Contents of section .eh_frame_hdr:

~~~
Hence, flag is:  
picoCTF{U51N6_Y0Ur_F1r57_F113_e5559d46}
