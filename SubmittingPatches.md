# How to submit a patch for the linux kernel #

Read :
  * /linux-2.6/Documentation/SubmittingPatches
  * /linux-2.6/Documentation/SubmitChecklist


## Make your change ##

Your code change should meet the requirements in:
Documentation/CodingStyle

Trivial violations can be checked with
scripts/checkpatch.pl
You should be able to justify any violations left in the patch

Your code should pass a sparse check cleanly.
  * http://kernel.org/pub/software/devel/sparse/


## Test your change ##

  * Your change should build cleanly:
    1. With all configurations of the Kernel area you are working on
      1. =y,n,m
    1. Cross compiled for some different architectures
    1. On allyesconfig, allnoconfig and allmodconfig

## Create the patch ##

```
cd linux-next
diff -up >../patches/MyNewPatch.txt
```

or using git

```
cd linux-next
git diff >../patches/MyNewPatch.txt
```

## test the patch ##

unpack a clean kernel and check your patch applies cleanly
```
mkdir linux-next
git-checkout -f
patch -p0 ../patches/MyNewPatch.txt
```

## test your mailer ##
Linux kernel patches are sent in emails as inline text, without MIME without attachments.
Because of this the **most common errors** in a first patch are wrapping or whitespace error introduced by a mailer. So it is important to determine how to send a patch in this format correctly.
To do this, simply mail the patch to yourself and apply it to a clean tree. (This is a simple but important step!)


## signed off by ##

## patch introduction ##

## who to send to ##

## what to do once your patch has been sent ##

## Links ##