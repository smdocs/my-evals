#FUSE - Userspace File System Framework

#### What is FUSE?

FUSE is a userspace filesystem framework.  It consists of a kernel module (fuse.ko), a userspace library (libfuse.*) and a mount utility
(fusermount).

One of the most important features of FUSE is allowing secure, non-privileged mounts.  This opens up new possibilities for the use of
filesystems.  A good example is sshfs: a secure network filesystem using the sftp protocol.

###### Golang Implementation of FUSE

- [Bazil Slides](https://bazil.org/talks/2013-06-10-la-gophers/#10)
- [Bazil Web site](http://bazil.org)
