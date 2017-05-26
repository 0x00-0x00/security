### \#\# Random tools

These are all random tools and tips lacking a home in this book. Hopefully they will one day find a place to live and prosper!

`binwalk --dd='.*' music.mp3` extract all mp3 or other types from a file.  
`netstat –ano 1 | find "Dest_IP_Addr"`  The -a parameter lists all the computer's connections and listening ports, while the -n parameter displays addresses and port numbers in numerical format. The -o parameter outputs the process ID \(PID\) responsible for the connection.

`Mimikatz` is a tool for attacking Windows secrets. Allows you to dump Kerberos secrets, create Golden Tickets, view plaintext credentials \(if wdigest is enabled\).



**listing files**

`ls -LR`

`grep -rnw '/path/to/somewhere/' -e "pattern"`

`find . -name "*.pdf" -type f`



**list all users**

cat /etc/passwd \| cut -d: -f1

grep -v -E "^\#" /etc/passwd \| awk -F: '$3 == 0 { print $1}' - list super users



**disable aslr**

ulimit -s unlimited



`find -name ".bash_history" -exec cat {} \; find / -user kent 2>/dev/null `list old commands left by users

`usermod -s /bin/bash username`  change shell for a specific user

