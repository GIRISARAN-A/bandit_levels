# 📘 OverTheWire Bandit Levels walkthrough 


This repository contains a step-by-step walkthrough of Bandit Wargame Levels 0 to 5, explaining how each password is obtained using basic Linux commands.

It is beginner-friendly and focuses on file handling, hidden files, and special filenames.


## 🌐 Game Access Details

Host: bandit.labs.overthewire.org
Port: 2220

SSH Login format:
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

# Level 0 → Level 1

Username: bandit0
Password: bandit0

Goal: Find the password stored in a file named `readme`.

Commands:
```bash
ls
cat readme
```

# Level 1 → Level 2

Goal: Password is stored in a file named `-`

Commands:
```bash
ls
cat ./-
```

# Level 2 → Level 3

Goal: Password is in a file named `spaces in this filename`

Commands:
```bash
ls
cat "spaces in this filename"
```

# Level 3 → Level 4

Goal: Password is inside a hidden file in the `inhere` directory.

Commands:
```bash
ls
cd inhere
ls -a
cat ...Hiding-From-You
```

# Level 4 → Level 5

Goal: Password is in the only human-readable file inside `inhere`.

Commands:
```bash
ls
cd inhere
ls
cat ./-file{00..09}
```

# 🧰 Commands Learned
```bash
ssh            # Remote login
ls             # List directory contents
cd             # Change directory
cat            # View file content
ls -a          # Show hidden files
./filename     # Access special filenames
"filename"     # Handle spaces
{00..09}       # Brace expansion
```

# 🏁 Conclusion

>Levels 0 → 5 teach fundamental Linux skills required for cybersecurity and CTF challenges.

-----

This repository documents the solutions and command usage for Bandit Levels.


## Skills Learned

- Encoding / Decoding
- File compression & extraction
- Hexdump analysis
- SSH authentication
- Port scanning
- SSL connections
- File comparison
- Privilege escalation basics


# 🛠️ Command Reference

## grep
Search for patterns inside files.

Syntax:
```bash
grep [options] pattern file

Example:
grep "password" data.txt
```

## sort
Sort lines alphabetically.
```bash
sort data.txt
```

## uniq
Remove duplicate lines.
```bash
uniq data.txt
```

## strings
Extract readable text from binary files.
```bash
strings file.bin
```

## base64
Decode / encode Base64 data.

Decode:
```bash
base64 -d data.txt
```

## tr
Translate or rotate characters.

ROT13 Example:
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

## tar
Archive / extract tar files.

Extract:
```bash
tar -xvf file.tar
```

## gzip / gunzip
```bash
gunzip file.gz
```

## bzip2 / bunzip2
```bash
bunzip2 file.bz2
```

## xxd
Create or reverse hexdumps.

Reverse:
```bash
xxd -r data.txt > file.bin
```

## mkdir
Create directories.
```bash
mkdir /tmp/myfolder
```

## cp
Copy files.
```bash
cp data.txt /tmp/myfolder
```

## mv
Move / rename files.
```bash
mv file.bin archive.gz
```

## file
Identify file type.
```bash
file data.bin
```
---

# 🌐 Networking Commands

## ssh
Remote login.
```bash
ssh user@host -p port
```

## telnet
Connect to ports.
```bash
telnet localhost 30000
```

## nc (netcat)
```bash
nc localhost 30000
```

## openssl s_client
```bash
openssl s_client -connect localhost:30001
```

## nmap
```bash
nmap -sV -p 31000-32000 localhost
```

# 📂 File Comparison
```bash
# diff

diff passwords.old passwords.new

# cat

cat readme

# ls

ls -la
```

# 🔐 setuid Binary Concept

Run file as owner:
```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```

# 📊 Command Usage Summary

| Command | Category | Level |
|--------|-----------|-------|
| base64 | Encoding | 10–11 |
| tr | Cipher | 11–12 |
| xxd | Hexdump | 12–13 |
| tar/gzip/bzip2 | Compression | 12–13 |
| ssh | Remote login | 13+ |
| nc/telnet | Networking | 14–16 |
| openssl | SSL | 15–16 |
| nmap | Scanning | 16–17 |
| diff | Compare | 17–18 |

---

# Conclusion

>Bandit Levels 10–20 teach Linux, networking, and cybersecurity fundamentals.
