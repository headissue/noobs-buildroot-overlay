[raspberry pi noobs](https://github.com/raspberrypi/noobs) buildroot overlay
============================================================================

The [raspberry pi noobs repository](https://github.com/raspberrypi/noobs) is based on [buildroot](http://buildroot.uclibc.org).
In [Commit f7e730a](https://github.com/raspberrypi/noobs/commit/f7e730ab05ee60503af46f7d866c5c956b83743c) it got updated to
[buildroot commit 083f853](https://github.com/buildroot/buildroot/commit/083f853).

This repository contains the changes between the base buildroot version and the one used by noobs.


How To Recreate
----------------

Extract the original buildroot next to the version in the noobs repository.
Then remove all identical files with [fdupes](http://en.wikipedia.org/wiki/Fdupes):

	fdupes -rdN ./buildroot ./buildroot-083f853

Now you have a big pile of empty folders. Delete them with

	cd buildroot
	find . -type d -empty -exec rmdir {} \;

Now you can look at a diff between the versions:

	diff -r ./buildroot ./buildroot-083f853 | grep -v "Only in buildroot-083"
