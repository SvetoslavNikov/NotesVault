11[[Linux Fundamentals]]

Here’s the updated table with the first and last columns swapped, and the first column removed:

|Example|Description|
|---|---|
|`grep -i "hello" file.txt`|Ignore case in the search|
|`grep "k" -r /path/to/directory`|Search recursively for the pattern "k" in all files in the current directory and subdirectories|
|`grep -n "hello" file.txt`|Print the matching lines along with their line numbers|
|`grep "hello" *.txt`|Search for the word "hello" in all `.txt` files in the current directory|
|`grep -v "hello" file.txt`|Invert search and return lines where the pattern does **not** appear|
|`grep -r "word" dir/dir/dir`|Search recursively for "word" in the directory `dir/dir/dir`|
|`grep -l "hello" *.txt`|Show only the filenames that contain the pattern|
|`touch newfile.txt`|Create an empty file|
|`touch ./myfiles/new.txt`|Create the file `new.txt` inside the `myfiles` directory|
|`tree /path/to/directory`|Display the directory structure as a tree|
|`mv oldname.txt newname.txt`|Move or rename files|
|`find . -name "file.txt"`|Find a file named `file.txt` starting from the current directory (case sensitive)|
|`find / -iname "*fil*"`|Find files whose names contain "fil" (case insensitive) starting from the root directory|
|`sudo updatedb`|Update the database used by `locate`|
|`locate file.txt`|Locate `file.txt` using the database built by `updatedb`|
|`which git`|Show the path of the `git` executable|
|`grep "hello" file.txt|wc -w`|
|`find .|wc -l`|
|`find / -name "file.txt" 2>/dev/null`|Discard error messages like "Permission denied" by redirecting them to null|

Let me know if you need further adjustments!
vim file
:Tutor

Example:

```shell-session
yakoti@htb[/htb]$ find / -type f -name *.conf -user root -size +20k -newermt 2020-03-03 -exec ls -al {} \; 2>/dev/null

-rw-r--r-- 1 root root 136392 Apr 25 20:29 /usr/src/linux-headers-5.5.0-1parrot1-amd64/include/config/auto.conf
-rw-r--r-- 1 root root 82290 Apr 25 20:29 /usr/src/linux-headers-5.5.0-1parrot1-amd64/include/config/tristate.conf
-rw-r--r-- 1 root root 95813 May  7 14:33 /usr/share/metasploit-framework/data/jtr/repeats32.conf
```

|**Option**|**Description**|
|---|---|
|`-type f`|Hereby, we define the type of the searched object. In this case, '`f`' stands for '`file`'.|
|`-name *.conf`|With '`-name`', we indicate the name of the file we are looking for. The asterisk (`*`) stands for 'all' files with the '`.conf`' extension.|
|`-user root`|This option filters all files whose owner is the root user.|
|`-size +20k`|We can then filter all the located files and specify that we only want to see the files that are larger than 20 KiB.|
|`-newermt 2020-03-03`|With this option, we set the date. Only files newer than the specified date will be presented.|
|`-exec ls -al {} \;`|This option executes the specified command, using the curly brackets as placeholders for each result. The backslash escapes the next character from being interpreted by the shell because otherwise, the semicolon would terminate the command and not reach the redirection.|
|`2>/dev/null`|This is a `STDERR` redirection to the '`null device`', which we will come back to in the next section. This redirection ensures that no errors are displayed in the terminal. This redirection must `not` be an option of the 'find' command.|