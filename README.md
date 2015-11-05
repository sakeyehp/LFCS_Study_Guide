# LFCS Study Guide
## Devin Nathan-Turner

This is imperfect studying material. It is solely designed for assisting in breaking down the domains and competencies
defined on the Linux Foundation's website.

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
