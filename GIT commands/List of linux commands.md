## "export PS1=" for customizing shell prompt

```
eg::::
hhv@12.32.65.98:/opt/hhv/jdjj$
export PS!='$'
$
```
## more command
```
more -n file1.txt
more -5 file1.txt
more -10 file1.txt
=======================
more +5 file1.txt >>>>>>>which show content from 5th line
```
## head and tail commands
```
head file.txt
head -10 file.txt
tail file.txt
tail -n file.txt
tail -10 file.txt
```
## tar command Examples
The `tar` command in Linux is used for archiving files. It's often used to create a single archive file (also called a "tarball") that contains multiple files and directories. Here's a basic syntax for using the `tar` command:

```bash
tar options archive_name files_or_directories
```

Here are some common options:

- `-c`: Create a new archive.
- `-x`: Extract files from an archive.
- `-v`: Verbose mode, print the names of the files being processed.
- `-f`: Specify the filename of the archive.
- `-z`: Compress the archive using gzip.
- `-j`: Compress the archive using bzip2.

To create a tarball of a directory, you can use the `-c` option to create, `-f` to specify the filename, and then list the directory or files you want to include in the archive:

```bash
tar -cvf archive.tar directory_or_file1 directory_or_file2 ...
```

For example, to create a tarball of a directory named `my_directory`, you would use:

```bash
tar -cvf my_directory.tar my_directory
```

If you want to compress the tarball using gzip, you can add the `-z` option:

```bash
tar -cvzf my_directory.tar.gz my_directory
```

And if you want to extract files from a tarball, you use the `-x` option:

```bash
tar -xvf archive.tar
```

Replace `archive.tar` with the name of the tarball you want to extract.

Remember to replace `archive_name` with the desired name of your tarball, and `files_or_directories` with the names of the files or directories you want to include in the archive.




