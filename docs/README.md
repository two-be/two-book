# Remote Copying With the scp Command

```
scp [-r] [[user1@]hostname1:]file1 ... [[user2@]hostname2:]file2
```

option | description
--- | ---
`-r` | Use to recursively copy entire directories.
`user1`, `user2` | Login account to use on the remote host.
`hostname1`, `hostname2` | The names of the remote host from or to which the file is to be copied.
`file1` | The file name or directory name to be copied. Several source file names may be included on one command line.
`file2` | The destination file name or directory name.

*example*
```
scp ./file.ext user:/home/dest
```
```
scp -r ./folder user:/home/dest
```