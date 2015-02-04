[raspberry pi noobs](https://github.com/raspberrypi/noobs) buildroot overlay
============================================================================

The [raspberry pi noobs repository](https://github.com/raspberrypi/noobs) contains an undefined version of [buildroot](http://buildroot.uclibc.org).
In [Issue #8](https://github.com/raspberrypi/noobs/issues/8) [@lurch](https://github.com/lurch) determined the version used is based on the git commit [e9b771283765e74792df6a05775383f6d4da2636](https://github.com/buildroot/buildroot/commit/e9b771283765e74792df6a05775383f6d4da2636).

This repository contains the changes between the base buildroot version and the one checked in.


How To Recreate
----------------

Extract the original buildroot next to the version in the noobs repository.
Then remove all identical files with [fdupes](http://en.wikipedia.org/wiki/Fdupes):

	fdupes -r ./buildroot ./buildroot-e9b771283765e74792df6a05775383f6d4da2636

Now you have a big pile of empty folders. Delete them with

	cd buildroot
	find . -type d -empty -exec rmdir {} \;

Now you can look at a diff between the versions:

	diff -r ./buildroot ./buildroot-e9b771283765e74792df6a05775383f6d4da2636 | grep -v "Only in buildroot-e9b"