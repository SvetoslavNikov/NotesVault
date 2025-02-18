[[Linux Fundamentals]]
Got it! Here's the list again without asterisks:

## 1. Pipe (`|`)

Passes the output of one command as input to another.

```sh
ls -l | grep ".txt"
```

## 2. Redirection Operators

### a) Output Redirection (`>`, `>>`)

- `>` Overwrites a file with the command’s output.
- `>>` Appends output to a file.

```sh
echo "Hello" > file.txt   # Overwrites file.txt
echo "World" >> file.txt  # Appends to file.txt
```

### b) Input Redirection (`<`)

Takes input from a file instead of standard input.

```sh
sort < names.txt
```

## 3. Logical Operators

### a) AND (`&&`)

Runs the second command only if the first one succeeds.

```sh
mkdir new_dir && cd new_dir
```

### b) OR (`||`)

Runs the second command only if the first one fails.

```sh
ping -c 1 google.com || echo "No internet"
```

## 4. Background and Job Control

### a) Background Execution (`&`)

Runs a command in the background.

```sh
firefox &
```

### b) `nohup` (No Hang-Up)

Runs a command that continues even after logout.

```sh
nohup myscript.sh &
```

## 5. Command Substitution (`$( )` or `` ` ` ``)

Executes a command and substitutes its output.

```sh
echo "Today is $(date)"
```

## 6. Concatenation (`;`)

Runs multiple commands sequentially, regardless of success or failure.

```sh
echo "Hello"; echo "World"
```

Let me know if you need anything else!