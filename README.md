Read the file called DISCLAIMER.

On Freebsd, type "gmake".
On other platforms, type "make" (as long as this is gnu make).

For FAQs, updated source code, and the lost chapter, see http://www.apuebook.com.
Please direct questions, suggestions, and bug reports to sar@apuebook.com.

Steve Rago
January 2013



# apue.3e

UNIX环境高级编程第三版

本书配套代码下载于http://apuebook.com/


make报错

```
[u1@h1 apue.3e]$ make
gcc -ansi -I../include -Wall -DLINUX -D_GNU_SOURCE   -c -o rwlock.o rwlock.c
gcc -ansi -I../include -Wall -DLINUX -D_GNU_SOURCE  timedlock.c -o timedlock  -L../lib -lapue -pthread -lrt -lbsd
gcc -ansi -I../include -Wall -DLINUX -D_GNU_SOURCE  barrier.c -o barrier  -L../lib -lapue -pthread -lrt -lbsd
/tmp/ccb9gvom.o: In function `thr_fn’:
barrier.c:(.text+0x6e): undefined reference to `heapsort’
collect2: ld 返回 1
make[1]: *** [barrier] 错误 1
make[1]: Leaving directory `/home/albert/Documents/progs/apue.3e/threads’
make: *** [all] 错误 1
```

是因为少库

解决方法：
```
在https://pkgs.org/download/libbsd,下载libbsd,libbsd-devel,我没用这里,直接用的下面的方法

或

wget http://elrepo.reloumirrors.net/testing/el6/x86_64/RPMS/libbsd-0.2.0-4.el6.elrepo.x86_64.rpm 

wget http://elrepo.reloumirrors.net/testing/el6/x86_64/RPMS/libbsd-devel-0.2.0-4.el6.elrepo.x86_64.rpm  

rpm -ivh libbsd-0.2.0-4.el6.elrepo.x86_64.rpm  

rpm -ivh libbsd-devel-0.2.0-4.el6.elrepo.x86_64.rpm  

```

再次make,通过

可以做相关测试和代码阅读了.
