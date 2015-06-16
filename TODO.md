# Kernel Testing #

This task is an important part of the kernel development process and does not require C programming skills. It is also a good place to start to learn about the kernel and the tools used to develop and mange it.

Once you have found a bug it is important to report it usefuly, see:
  * /linux-2.6/REPORTING-BUGS
  * http://www.chiark.greenend.org.uk/~sgtatham/bugs.html

Oops reporting tool @
  * http://www.kerneloops.org/


## Compile the latest kernel release and test on your home machine ##

To compile and boot a new kernel follow the instructions here :
  * http://www.cyberciti.biz/tips/compiling-linux-kernel-26.html
or more detailed instructions here:
  * http://www.digitalhermit.com/linux/Kernel-Build-HOWTO.html

Testing is kind of arbitry, you can test the kernel how you like. Just booting it and making sure it runs on a large population of hardware is one of the best things a kernel janitor can do.


For information on more detailed testing and benchmarking see:

  * http://linuxquality.sunsite.dk/articles/testsuites/
  * http://sourceforge.net/projects/ltp/
  * http://www.ibm.com/developerworks/linux/library/l-stress/index.html

## Compile random .configs ##

Ramdom .configs are more likely to find bugs than the distribution .configs.

Generate random .config's and compile.

```
@ubuntu:~/linux-2.6$ make randconfig
@ubuntu:~/linux-2.6$ make -j2 v=1
```

Boot on your machine if compatible, and test. (Requires knowledge of how .config works and what hardware you have on your system)
When the kernel does not compile, or the testing shows problems, report them.


## Compile for multiple architectures ##
A little more obscure is cross compiling the latest kernel (perhaps even.random configs) for multiple architectures.
To cross compile follow the instructions here :
  * http://kernelnewbies.org/FAQ/KernelCrossCompilation
  * http://wiki.ppckernel.org/w/Cross_compiling_a_64-bit_PowerPC_Linux_Kernel


## Run linux next tree ##
Linux next is the tree that is built as a testbed for the **next** kernel release.
This is the most likely place to find problems, and therefore is the most useful to test, and the most likely to break your machine.
Git tree at:
  * git://git.kernel.org/pub/scm/linux/kernel/git/sfr/linux-next.git
Tar balls at:
  * http://www.kernel.org/pub/linux/kernel/people/sfr/linux-next/




# Bug Hunting/Fixing #

This is the most usefull task a developer can do!
Requires C programming skills, problem solving etc but is the most rewarding.
Also it is a good way to get into the kernel and find out which area's interest you.
General bug finding information:
  * linux-2.6/Documentation/BUG-HUNTING


## Linux-Staging Tree ##

The linux staging tree is a tree for drivers, filesystems and other reasonable sized features that are not yet ready for mainline inclusion. This means that all the patches here are in need of work, including sparse fixes and cleanup type patches.

  1. http://kerneltrap.org/Linux/Introducing_the_Linux_Staging_Tree
git tree at:
  1. git://git.kernel.org/pub/scm/linux/kernel/git/gregkh/staging.git


## Coverity defects ##
Coverity is an advanced static analysis tool which regularly scans the linux kernel.
It has a large database of suspect defects, and if you can read and write C code proficiently, this is a sure way to find a bug, send a fix in and get some of your code in the kernel
  * http://scan.coverity.com/


## Bugzilla ##
Bugzilla has a list of bug reports, find one you like, try to diagnose the problem, then look at the code and try to find the bug.
  * http://bugzilla.kernel.org/

## Kernel Oops debugging ##
A more chalenging task is to analyse kernel oop's data and diagnose the problem (and fix if able).
This task is harder, but these bugs are not just theoretical, they are getting hit by real people. Also this is a good way for a skilled embedded C developer to learn a bit more about the lower level workings.

  * http://www.kerneloops.org/
  * linux-2.6/Documentation/oops-tracing.txt
  * http://mail.nl.linux.org/kernelnewbies/2003-08/msg00347.html
  * http://kerneltrap.org/Linux/Decoding_Oops
  * http://kerneltrap.org/Linux/Further_Oops_Insights
  * http://kerneltrap.org/Linux/Tracking_Kernel_Oops


# API conversions #

API conversions sometimes take a **long** time in the linux kernel.
Kernel Janitors can help out in this area, but often the low hanging fuit are quickly picked and only the more dificault conversions are left.

## request\_firmware() ##
David Woodhouse is workig on getting drivers which load firmware into the device converted over to use request\_firmware().
Initial patch:
  * http://lwn.net/Articles/283759/
Article:
  * http://lwn.net/Articles/284104/
git tree :
  * git.infradead.org/users/dwmw2/firmware-2.6.git
List of suspect drivers:
  * http://www.fsfla.org/svn/fsfla/software/linux-libre/scripts/deblob-2.6.25
Documentation:
  * http://www.mjmwired.net/kernel/Documentation/firmware_class/



# API/Feature Removel #



**TODO is a work in progress, please help out**