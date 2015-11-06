# LFCS Study Guide

This is imperfect studying material. It is solely designed for assisting in breaking down the domains and competencies defined on the Linux Foundation's website.

### Command Line
#### Creating Files Without Using an Editor

There are two standard ways to create a file directly from the command line and fill it with content.

The first is to use *echo*:

    $ echo line one > myfile
    $ echo line two >> myfile
    $ echo line three >> myfile

As will be covered in a later section:

    >  --> redirect output of a command to a file
    >> --> append new output to an existing file (if exists)

The second is to use *cat*:

    $ cat << EOF > myfile
    > line one
    > line two
    > line three
    > EOF
    $

Both techniques will produce [this file](1.sh).

#### sudo

*sudo* allows users to run programs using the secuirty privileges of another user, genrally root (superuser). 

If your system does not already have sudo set up and enabled, you need to do the following steps:
* As the superuser, create a configuration file to enable the user account to use sudo. Typically, this file is created in the `/etc/sudoers.d/` directory with the name of the file the same as the username. For example, let's say the username is "student". You can create the configuration file for "student" by doing this:

`# echo "student ALL=(ALL) ALL" > /etc/sudoers.d/student`

Some distributions will complain if you don't also change permissions on the file by doing:

`# chmod 440 /etc/sudoers.d/student`

#### Locating Applications

In general, executable programs should live in the following directories:

    /bin
    /usr/bin
    /sbin
    /usr/sbin
    /opt

One way of locating programs is to employ the *which* utility. For example:

    $ which diff
    /usr/bin/diff

If which doesn't find the program, *whereis* is a good alternative:

    $ whereis diff
    diff: /usr/bin/diff /usr/bin/X11/diff /usr/share/man/man1/diff.1.gz

#### Absolute and Relative Paths

There are two ways to identify paths:
1. *Absolute pathname*: An absolute pathname begins with the root directory and follows the tree, branch by branch, until it reaches the desired directory or file. Absolute paths start with a /.
2. *Relative pathname*: A relative pathname starts from the present working directory. Relative paths never start with a /.

Most of the time, using the relative path is simpler:

    $ cd ~ -> navigates to home directory of user
    $ cd ../ -> navigates to branch above

However, sometimes using the absolute path makes more sense:

    $ cd /usr/bin -> absolute
    $ cd ../../usr/bin -> relative

