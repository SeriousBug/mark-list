# mark-list

Mark files, then print them out.

This is useful when you are trying to mass process files, but the files you want
to select do not fit any specific pattern. This usually makes it hard to pick
all the files automatically (e.g. using `find`), so it may be desirable to
manually pick the files. See the following example:

``` sh
$ mark-list --clear  # Make sure nothing is left over from a previous usage
$ mark-list my-video.mp4  # Choose a file
Marked 1 file.
$ mark-list *.webm  # Choose many files
Marked 3 files.
$ cd Downloads
$ mark-list last.mpg  # You can go to other directories and keep marking
Marked 1 file.
$ for file in `mark-list --list` ; do ffmpeg -i "${file}" "${file}.mkv" ; done
# ... converts all marked videos ...
```

## Installation

Download the file `mark-list` from this repository, and place it somewhere on
your `$PATH`. Then, make sure the file is marked as executable with `chmod +x
mark-list`.

You must have `bash` and `realpath` installed.
