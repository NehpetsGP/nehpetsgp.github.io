+++
date = '2025-12-28T12:27:30-05:00'
draft = true
title = 'CLI_Commands'
+++

Working in different terminal emulators on different computers can be frustrating if
you don't spend a lot of time in each of them. In my personal life I primarily use Bash 
on Linux, while in my professional life I work on Windows with CMD & Powershell.

To save myself aggravation I put together a quick reference table showing common
Bash commands with their equivalent in CMD & Powershell.

Below is that reference table, feel free to copy or add commands in the comments that you 
have found helpful in your workflow.

| Description                          | Bash Syntax                          | CMD Syntax                           | PowerShell Syntax                            |
|--------------------------------------|--------------------------------------|--------------------------------------|----------------------------------------------|
| Print working directory              | `pwd`                               | `cd`                                | `Get-Location`                              |
| List directory contents              | `ls` or `ls -l` for details         | `dir`                               | `Get-ChildItem`                             |
| Change directory                     | `cd /path`                          | `cd \path`                          | `Set-Location /path`                        |
| Copy file                            | `cp source dest`                    | `copy source dest`                  | `Copy-Item source dest`                     |
| Move or rename file                  | `mv source dest`                    | `move source dest`                  | `Move-Item source dest`                     |
| Delete file                          | `rm file`                           | `del file`                          | `Remove-Item file`                          |
| Create directory                     | `mkdir dir`                         | `mkdir dir` or `md dir`             | `New-Item -ItemType Directory dir`          |
| Remove empty directory               | `rmdir dir`                         | `rmdir dir` or `rd dir`             | `Remove-Item dir`                           |
| Remove directory with contents       | `rm -r dir`                         | `rmdir /s dir` or `rd /s dir`       | `Remove-Item -Recurse dir`                  |
| View file contents                   | `cat file`                          | `type file`                         | `Get-Content file`                          |
| Search for pattern in file           | `grep "pattern" file`               | `findstr "pattern" file`            | `Select-String "pattern" file`              |
| Pipe output                          | `command1 \| command2`              | `command1 \| command2`              | `command1 \| command2`                      |
| Redirect output (overwrite)          | `command > file`                    | `command > file`                    | `command \| Out-File file`                  |
| Redirect output (append)             | `command >> file`                   | `command >> file`                   | `command \| Out-File -Append file`          |
| Echo text                            | `echo "text"`                       | `echo text`                         | `Write-Output "text"`                       |
| Create empty file                    | `touch file`                        | `type nul > file`                   | `New-Item file`                             |
| Find files                           | `find /path -name "*.txt"`          | `dir /s /b *.txt`                   | `Get-ChildItem -Recurse -Filter "*.txt"`    |
| List processes                       | `ps`                                | `tasklist`                          | `Get-Process`                               |
| Kill process by ID                   | `kill PID`                          | `taskkill /PID PID`                 | `Stop-Process -Id PID`                      |
| Ping a host                          | `ping host`                         | `ping host`                         | `Test-Connection host`                      |
| View last lines of file              | `tail -n 10 file`                   | `more + (line count - 10) file`     | `Get-Content -Tail 10 file`                 |
| Count lines/words/characters         | `wc file`                           | `find /c /v "" file` (lines only)   | `Get-Content file \| Measure-Object -Line -Word -Character` |
| Sort file contents                   | `sort file`                         | `sort file`                         | `Get-Content file \| Sort-Object`           |
| Get unique lines                     | `uniq file`                         | `sort file \| findstr /x /v /b /e /g:file` (complex) | `Get-Content file \| Select-Object -Unique` |
| Compare files                        | `diff file1 file2`                  | `fc file1 file2`                    | `Compare-Object (Get-Content file1) (Get-Content file2)` |
| Download file from URL               | `wget url -O file`                  | `curl url -o file` (if curl available) | `Invoke-WebRequest -Uri url -OutFile file`  |
| Set environment variable             | `export VAR=value`                  | `set VAR=value`                     | `$env:VAR = "value"`                        |
| Get environment variable             | `echo $VAR`                         | `echo %VAR%`                        | `$env:VAR`                                  |
| Get command help                     | `man command`                       | `command /?`                        | `Get-Help command`                          |
| Display username                     | `whoami`                            | `whoami`                            | `whoami`                                    |
| System information                   | `uname -a`                          | `systeminfo`                        | `Get-ComputerInfo`                          |
| Compress files (tar.gz)              | `tar -czf archive.tar.gz files`     | No built-in, use third-party        | `Compress-Archive -Path files -DestinationPath archive.zip` (zip) |
| Extract archive                      | `tar -xzf archive.tar.gz`           | No built-in, use third-party        | `Expand-Archive -Path archive.zip` (zip)    |


