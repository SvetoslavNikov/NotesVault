## File Descriptors

A file descriptor is a unsigned integer value used to processes to identify open files.
### 1. STDIN - 0
(Data stream for Input)
### 2. STDOUT - 1
(Data stream for Output)
### 3. STDERR - 2
(Data Stream for Out that relates to an error occurring)

## Redirecting STDOUT & STDERR (error & output)

```bash
find /etc/ -name passwd 2>/dev/null > results.txt
#Permission denied logs goes to null, where they are discarded
#The left results are saved in file results.txt
# >> would append them to the existing data in the file
```
## Redirecting STDIN (input)

```bash
cat < text.txt
#the data from text.txt is given to the cat command as an input
```

## "<<" = Until it reaches

```bash
cat << EOF > writings.txt
#  << means until you reach
# EOF - end of a file, can use end too
```

## " | " Pipes operator

```
find / -name *.conf 2>/dev/null | grep systemd | wc -l

#stderr - discarded (null)
#results from find -> selected only paths with systemd -> count lines
```