
[[Linux Fundamentals]]

```
<username>@<hostname><current working directory>$
```

```
<username>@<hostname>[~]$
```
**"**~**"** = home directory for a user
**$** = user

Log in as Root
"**#**" = root
```
root@htb[/htb]#
```

### Customizing the prompt

By customizing the PS1 variable in Linux system.

| Special Character | Description                                |
| ----------------- | ------------------------------------------ |
| `\d`              | Date (Mon Feb 6)                           |
| `\D{%Y-%m-%d}`    | Date (YYYY-MM-DD)                          |
| `\H`              | Full hostname                              |
| `\j`              | Number of jobs managed by the shell        |
| `\n`              | Newline                                    |
| `\r`              | Carriage return                            |
| `\s`              | Name of the shell                          |
| `\t`              | Current time 24-hour (HH:MM:SS)            |
| `\T`              | Current time 12-hour (HH:MM:SS)            |
| `\@`              | Current time                               |
| `\u`              | Current username                           |
| `\w`              | Full path of the current working directory |

