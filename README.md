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
<<<<<<< HEAD
$gdb -g overflow 
(gdb) run
(gdb) info req eip
(gdb) q
```
=======
gcc -ggdb -mpreferred-stack-boundary=2 -fno-stack-protector -o overflow
``` 
>>>>>>> 807f9e0a35570a65e02d87532379da29737bc17f
