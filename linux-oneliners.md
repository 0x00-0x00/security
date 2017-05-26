# Linux

`pwd` Print working directory

`cd` Change directory

`cd ~` Change directory to your home directory

`cd -` Go back to previous directory

`ls` List files in directory

`ls -ltr` Sort list by last modified. -time -reverse

`file` Show info about file. What type of file it is. If it is a binary or text file for example.

`cat` Output content of file.

`less` Output file but just little bit at a time. Use this one. Not`more`.

Use`/searchterm`to search. It is the same command as in vim.`n`to scroll to next search result. Press`q`to quit.

`more` Output file but just little bit at a time.`less`is better.

`touch` Create a new file.

`cp` Copy

`mkdir` Make directory. `-p` argument creates directory path

`rm` Remove file

`history` Show commands history

`sudo` List what rights the sudo user has.  `sudo -l`

Sudo config file is usually in `/etc/sudoers`

`find / -name file 2 >/dev/null` Send all permissions denied outputs to /dev/null

`sudo updatedbU`pdate database

`locate filename` Locate files

```
which bash

# Usually outputs: /bin/bash
```

Count lines in file

`$ wc -l [file]`

Create tar archive

```
$ tar cvf [archiveName.tar] [dirName/]
```

Extract tar archive

```
$ tar xvf [archiveName.tar]
```

Search for string within file \(non-case sensitive\)

```
$ grep –i "pattern" [file]
```

Inverse search: Exclude string from output

```
$ [command] | grep –v "pattern"
```

Find filenames matching a string \(non-case sensitive\)

```
$ find –iname "fileName"
```

Avoid matching substrings, only keeping full words in file

```
$ grep –w “pattern” [file]
```

Find IP valid addresses in a file

```
$ cat [file] | grep -oE "\b(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?\.){3}(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\b"
```

Add line number for all non-empty-lines in a file

```
$ sed '/./=' [file] | sed 'N; s/\n/ /'
```

File transfer with Netcat

```
[server]$ nc –v –w 30 –p 4444 –l 
>
 [file]
[client]$ nc –v –w 2 [ServerIP] 4444 
<
 [file]
```



