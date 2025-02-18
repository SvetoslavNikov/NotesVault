
## Penetration test assignment

Organize the workflow. Split the assignment into different stages based on Operating System or based on the task category: 
```shell-session
yakoti@htb[/htb]$ tree .
.
└── Penetration-Testing
	│
	├── Pre-Engagement
	│       └── ...
    ├── Linux
    │   ├── Information-Gathering
    │   │   └── ...
    │   ├── Vulnerability-Assessment
    │   │   └── ...
    │   ├── Exploitation
    │   │   └── ...
    │   ├── Post-Exploitation
    │   │   └── ...
    │   └── Lateral-Movement
    │       └── ...
    ├── Windows
    │   ├── Information-Gathering
    │   │   └── ...
    │   ├── Vulnerability-Assessment
    │   │   └── ...
    │   ├── Exploitation
    │   │   └── ...
    │   ├── Post-Exploitation
    │   │   └── ...
    │   └── Lateral-Movement
    │       └── ...
    ├── Reporting
    │   └── ...
	└── Results
	    └── ...
```
or like this:
```shell-session
yakoti@htb[/htb]$ tree .

.
└── Penetration-Testing
	│
	├── Pre-Engagement
	│       └── ...
    ├── Network-Pentesting
	│       ├── Linux
	│       │   ├── Information-Gathering
	│		│   │   └── ...
	│       │   ├── Vulnerability-Assessment
    │       │   │	└── ...
    │       │	└── ...
    │       │    	└── ...
    │		├── Windows
    │ 		│   ├── Information-Gathering
    │		│   │   └── ...
    │		│   └── ...
    │       └── ...
    ├── WebApp-Pentesting
	│       └── ...
    ├── Social-Engineering
	│       └── ...
    ├── .......
	│       └── ...
    ├── Reporting
    │   └── ...
	└── Results
	    └── ...
```

## Bookmarks

**This list of bookmarks will be seen by third parties sooner or later.**
1. Create an account for penetration testing purposes only
2. Customer-related bookmarks should never be saved

## Password Manager

problems with passwords:

1. **Complexity**
2. **Re-usage**
3. **Remembering**

"**1Password**"/ "**Bitwarden**" solves that
- Synchronize across all devices and browsers
- Only the person with the master password can access passwords unencrypted value
- Autogenerate complex passwords
- Folders, notes
- Cards, Personal info, Protected notes

Benefit for pen tester: 
**Even if the device is compromised and keylogged using Pass-manager with 2FA we are safe**

## Process
### 1. Gathering Information
-  Every possible source
### 2. Processing information - taking notes, mind maps
-  **Obsidian**
- **Xmind** - for mind maps
- https://excalidraw.com/ - is better for maps in my opinion
### 3. Results - saving everything that could help us later
- **Ghostwriter**: Markdown editor for writing, focused on simplicity and distraction-free writing.
-  **PwnDoc**: A penetration testing reporting tool used for creating structured security reports.
### 4. Logging: 
- **Linux:**
	-  **script-exit** command saves everything in the terminal after it.
			 file name: `<date>-<start time>-<name>.log
			 `script 03-21-2021-0200pm-exploitation.log`
	- configure detailed prompt 
```bash
export PS1="\[\033[1;32m\]\342\224\200\$([[ \$(/opt/vpnbash.sh) == *\"10.\"* ]] && echo \"[\[\033[1;34m\]\$(/opt/vpnserver.sh)\[\033[1;32m\]]\342\224\200[\[\033[1;37m\]\$(/opt/vpnbash.sh)\[\033[1;32m\]]\342\224\200\")[\[\033[1;37m\]\u\[\033[01;32m\]@\[\033[01;34m\]\h\[\033[1;32m\]]\342\224\200[\[\033[1;37m\]\w\[\033[1;32m\]]\n\[\033[1;32m\]\342\224\224\342\224\200\342\224\200\342\225\274 [\[\e[01;33m\]$(date +%D-%r)\[\e[01;32m\]]\\$ \[\e[0m\]"
```
result: 
```bash
─[VPNServer]─[10.10.x.x]─[user@hostname]─[/current/directory]
└──▼ [01/29/25-10:30:00 AM]$
``` 
.
	- for single commands output saved in file + shown in terminal: 
			 
```Shell
some_long_running_command | tee output.txt
```
			 
	- for single commands output saved in file:
			 
```shell-session
 ./custom-tool.py 10.129.28.119 > logs.custom-tool
```

- **Windows:**

```powershell-session
C:\> Start-Transcript -Path "C:\Pentesting\03-21-2021-0200pm-exploitation.log"

Transcript started, output file is C:\Pentesting\03-21-2021-0200pm-exploitation.log

C:\> ...SNIP...
C:\> Stop-Transcript

```

```powershell-session
C:\> .\custom-tool.ps1 10.129.28.119 > logs.custom-tool
```

```powershell-session
C:\> .\custom-tool.ps1 10.129.28.119 | Out-File -Append logs.custom-tool
```


### 5. Screenshots
- For gif and screen recording you can use **Peek**
- For screenshots on Linux **Flameshot**
