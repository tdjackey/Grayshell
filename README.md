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


##Example3 : Shellcode.c
```
gcc -ggdb -mpreferred-stack-boundary=2 -fno-stack-protector -z execstack -o shellcode shellcode.c
```


##Example4 : Repeat return address

```
gcc -o get_sp get_sp.c
```

### forbidden ASLR
```
echo "0" > /proc/sys/kernel/randomize_va_space 
``` 

## peercast 
```
http://peercast.sourcearchive.com/downloads/0.1214.toots.svn20051112/
```
