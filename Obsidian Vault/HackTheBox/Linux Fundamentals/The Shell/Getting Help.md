[[Linux Fundamentals]]
Get help for the `ls` command:

```shell-session
yakoti@htb[/htb]$ man <tool>
```
```shell-session
yakoti@htb[/htb]$ man ls
```
```shell-session
LS(1)                            User Commands                           LS(1)

NAME
       ls - list directory contents

SYNOPSIS
       ls [OPTION]... [FILE]...

DESCRIPTION
       List  information  about  the FILEs (the current directory by default).
       Sort entries alphabetically if none of -cftuvSUX nor --sort  is  speci‐
       fied.
...
```

See every way of use for the command
```shell-session
yakoti@htb[/htb]$ ls --h or --help
```

Search the descriptions for instances of a given keyword.
```shell-session
yakoti@htb[/htb]$ apropos <keyword>
```

```shell-session
yakoti@htb[/htb]$ apropos sudo

sudo (8)             - execute a command as another user
sudo.conf (5)        - configuration for sudo front end
sudo_plugin (8)      - Sudo Plugin API
sudo_root (8)        - How to run administrative commands
sudoedit (8)         - execute a command as another user
sudoers (5)          - default sudo security policy plugin
sudoreplay (8)       - replay sudo session logs
visudo (8)           - edit the sudoers file
```

or just visit https://explainshell.com/
