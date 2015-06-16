Kernel Janitors FAQ

Q: What is Kernel Janitors?
A: It is a project to help wannabe kernel hackers get their feet wet
> while doing something useful for the community.

Q: What will I be doing?
A: Basically, cleaning up the kernel.
> You can look at TODO for some example tasks.

Q: Prerequisites?
A: Knowledge of C, being able to compile and boot Linux kernel.

Q: What documents should i read?
A: SubmittingPatches, CodingStyle from Documentation/ .
> http://www.zip.com.au/~akpm/linux/patches/stuff/tpp.txt
> and http://linux.yyz.us/patch-format.html are good to read also.

Q: What version should I be patching against?
A: Latest "linus" (2.6.x-rcY from kernel.org).
> Be sure to check -mm and -kj trees to see if someone already did that.

Q: Where should I send patches to?
A: Mailing list: kernel-janitors@lists.osdl.org
> If you feel confident enough, you can CC: someone from MAINTAINERS too.

Q: I have lots of patches that do the same thing. Can I just send them in
> one mail?
A: No, but don't send them in lots of small mails either. Try splitting
> them up per subsystem (drivers/net/, fs/ext3/...). See here:
> http://marc.theaimsgroup.com/?l=linux-kernel&m=112105809816217&w=2
> for details.

Q: Where can I find janitors?
A: On our mailing list and #kerneljanitor at irc.oftc.net

Q: I got some negative replies. Am I just wasting peoples' time?
A: A nice motivational post from Linus: http://lkml.org/lkml/2004/12/20/255