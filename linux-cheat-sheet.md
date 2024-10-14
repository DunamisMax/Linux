# Linux Command Cheat Sheet

A comprehensive guide to essential Linux commands.

## Table of Contents

1. [Basic Commands](#1-basic-commands)
2. [File Management](#2-file-management)
3. [Directory Navigation](#3-directory-navigation)
4. [File Permissions](#4-file-permissions)
5. [Process Management](#5-process-management)
6. [Network Commands](#6-network-commands)
7. [File Compression](#7-file-compression)
8. [Disk Usage](#8-disk-usage)
9. [Text Processing](#9-text-processing)
10. [Searching](#10-searching)
11. [System Information](#11-system-information)
12. [Package Management](#12-package-management)
13. [Users and Groups](#13-users-and-groups)
14. [SSH Commands](#14-ssh-commands)
15. [Miscellaneous Commands](#15-miscellaneous-commands)
16. [Keyboard Shortcuts](#16-keyboard-shortcuts)
17. [Environment Variables](#17-environment-variables)

---

## 1. Basic Commands

- `pwd`  
  Print Working Directory – Displays the current directory path.

- `whoami`  
  Shows the current username.

- `date`  
  Displays or sets the system date and time.

- `cal`  
  Displays a calendar.

- `echo [text]`  
  Outputs the specified text.

- `man [command]`  
  Shows the manual page for a command.

- `clear`  
  Clears the terminal screen.

- `exit`  
  Exits the current shell session.

[Back to Top](#table-of-contents)

---

## 2. File Management

- `ls`  
  Lists files and directories.

  - `ls -l`  
    Detailed listing with permissions.

  - `ls -a`  
    Includes hidden files.

- `cp [source] [destination]`  
  Copies files or directories.

- `mv [source] [destination]`  
  Moves or renames files or directories.

- `rm [file]`  
  Removes files.

  - `rm -r [directory]`  
    Removes directories and their contents recursively.

  - `rm -f [file]`  
    Forces removal without confirmation.

- `touch [file]`  
  Creates an empty file or updates the timestamp.

- `cat [file]`  
  Displays the contents of a file.

- `more [file]`  
  Views file contents one screen at a time.

- `less [file]`  
  Similar to `more` but with backward movement.

- `head [file]`  
  Displays the first 10 lines of a file.

  - `head -n [number] [file]`  
    Displays the first `[number]` lines.

- `tail [file]`  
  Displays the last 10 lines of a file.

  - `tail -n [number] [file]`  
    Displays the last `[number]` lines.

- `mkdir [directory]`  
  Creates a new directory.

- `rmdir [directory]`  
  Removes an empty directory.

- `ln -s [target] [link_name]`  
  Creates a symbolic link to a file or directory.

[Back to Top](#table-of-contents)

---

## 3. Directory Navigation

- `cd [directory]`  
  Changes the current directory.

- `cd`  
  Changes to the home directory.

- `cd ..`  
  Moves up one directory level.

- `cd -`  
  Switches to the previous directory.

- `pushd [directory]`  
  Saves the current directory and moves to `[directory]`.

- `popd`  
  Returns to the directory saved by `pushd`.

[Back to Top](#table-of-contents)

---

## 4. File Permissions

- `chmod [permissions] [file]`  
  Changes the access permissions of a file.

  - Numeric mode (e.g., `chmod 755 file`):

    | Number | Permission    |
    | ------ | ------------- |
    | 0      | No permission |
    | 1      | Execute       |
    | 2      | Write         |
    | 4      | Read          |

- `chown [owner]:[group] [file]`  
  Changes the owner and group of a file.

- `chgrp [group] [file]`  
  Changes the group ownership.

- `umask [mask]`  
  Sets default file creation permissions.

[Back to Top](#table-of-contents)

---

## 5. Process Management

- `ps`  
  Displays information about active processes.

  - `ps aux`  
    Shows all running processes.

- `top`  
  Real-time process monitoring.

- `htop`  
  Enhanced version of `top` (may require installation).

- `kill [PID]`  
  Terminates a process by its Process ID.

  - `kill -9 [PID]`  
    Forcefully terminates a process.

- `killall [process_name]`  
  Kills all processes with the specified name.

- `bg`  
  Resumes a suspended job in the background.

- `fg`  
  Brings a background job to the foreground.

- `jobs`  
  Lists all background and suspended jobs.

- `nice -n [priority] [command]`  
  Starts a process with a specified priority.

- `renice [priority] [PID]`  
  Changes the priority of an existing process.

[Back to Top](#table-of-contents)

---

## 6. Network Commands

- `ifconfig`  
  Displays or configures a network interface.

- `ip addr`  
  Shows IP addresses assigned to all interfaces.

- `ping [host]`  
  Checks connectivity to a host.

- `nslookup [domain]`  
  Queries DNS to obtain domain name or IP address mapping.

- `dig [domain]`  
  Fetches DNS information about a domain.

- `wget [URL]`  
  Downloads files from the internet.

- `curl [URL]`  
  Transfers data from or to a server.

- `ssh [user]@[host]`  
  Connects to a remote host via SSH.

- `scp [source] [destination]`  
  Securely copies files between hosts.

- `netstat -tulnp`  
  Displays network connections and listening ports.

- `traceroute [host]`  
  Shows the path packets take to reach a host.

- `nmap [host]`  
  Scans for open ports on a host.

[Back to Top](#table-of-contents)

---

## 7. File Compression

- `tar -cf [archive.tar] [files]`  
  Creates an archive from files.

- `tar -xf [archive.tar]`  
  Extracts files from an archive.

- `tar -czf [archive.tar.gz] [files]`  
  Creates a compressed archive with gzip.

- `tar -xzf [archive.tar.gz]`  
  Extracts a gzip compressed archive.

- `gzip [file]`  
  Compresses a file with gzip.

- `gunzip [file.gz]`  
  Decompresses a gzip compressed file.

- `zip [archive.zip] [files]`  
  Creates a zip archive.

- `unzip [archive.zip]`  
  Extracts a zip archive.

- `rar a [archive.rar] [files]`  
  Creates a rar archive (requires `rar`).

- `unrar x [archive.rar]`  
  Extracts a rar archive.

[Back to Top](#table-of-contents)

---

## 8. Disk Usage

- `df -h`  
  Shows disk space usage in human-readable format.

- `du -h [file/dir]`  
  Displays the size of files or directories.

- `du -sh *`  
  Summarizes disk usage of each item in the current directory.

- `mount`  
  Lists mounted filesystems.

- `umount [device]`  
  Unmounts a mounted filesystem.

[Back to Top](#table-of-contents)

---

## 9. Text Processing

- `grep [pattern] [file]`  
  Searches for a pattern in files.

  - `grep -r [pattern] [directory]`  
    Recursively searches files in a directory.

- `sed 's/[pattern]/[replacement]/g' [file]`  
  Stream editor for filtering and transforming text.

- `awk '{commands}' [file]`  
  Pattern scanning and processing language.

- `sort [file]`  
  Sorts lines of text files.

- `uniq [file]`  
  Removes duplicate lines.

- `tr '[set1]' '[set2]'`  
  Translates or deletes characters.

- `cut -d'[delimiter]' -f[field_number] [file]`  
  Removes sections from each line.

- `wc [file]`  
  Counts lines, words, and bytes.

  - `wc -l`  
    Counts lines.

  - `wc -w`  
    Counts words.

  - `wc -c`  
    Counts bytes.

- `paste [file1] [file2]`  
  Merges lines of files.

[Back to Top](#table-of-contents)

---

## 10. Searching

- `find [path] -name [pattern]`  
  Searches for files matching a pattern.

  - `find / -type f -name "filename"`  
    Searches the entire system for a file.

- `locate [filename]`  
  Finds files by name using a database.

- `which [command]`  
  Shows the full path of shell commands.

- `whereis [command]`  
  Locates the binary, source, and manual pages.

- `type [command]`  
  Displays how a command would be interpreted.

[Back to Top](#table-of-contents)

---

## 11. System Information

- `uname -a`  
  Displays kernel and system information.

- `hostname`  
  Shows or sets the system's hostname.

- `uptime`  
  Shows how long the system has been running.

- `free -h`  
  Displays memory usage.

- `lshw`  
  Lists hardware configuration (may need `sudo`).

- `lsblk`  
  Lists block devices.

- `lspci`  
  Lists PCI devices.

- `lsusb`  
  Lists USB devices.

- `dmidecode`  
  Shows BIOS and hardware details (requires `sudo`).

- `df -h`  
  Disk space usage.

- `last`  
  Lists last logged in users.

- `dmesg`  
  Prints kernel ring buffer messages.

- `cat /proc/cpuinfo`  
  CPU information.

- `cat /proc/meminfo`  
  Memory information.

[Back to Top](#table-of-contents)

---

## 12. Package Management

### Debian/Ubuntu (APT)

- `sudo apt update`  
  Updates package lists.

- `sudo apt upgrade`  
  Upgrades all installed packages.

- `sudo apt install [package]`  
  Installs a new package.

- `sudo apt remove [package]`  
  Removes a package.

- `sudo apt search [package]`  
  Searches for a package.

- `sudo apt autoremove`  
  Removes unnecessary packages.

### RedHat/CentOS/Fedora (YUM/DNF)

- `sudo yum update`  
  Updates all packages.

- `sudo yum install [package]`  
  Installs a new package.

- `sudo yum remove [package]`  
  Removes a package.

- `sudo dnf upgrade`  
  Upgrades all packages (Fedora).

- `sudo dnf install [package]`  
  Installs a new package (Fedora).

### Arch Linux (Pacman)

- `sudo pacman -Syu`  
  Updates the system.

- `sudo pacman -S [package]`  
  Installs a package.

- `sudo pacman -R [package]`  
  Removes a package.

[Back to Top](#table-of-contents)

---

## 13. Users and Groups

- `sudo adduser [username]`  
  Creates a new user.

- `sudo deluser [username]`  
  Removes a user.

- `sudo passwd [username]`  
  Changes a user's password.

- `sudo groupadd [groupname]`  
  Creates a new group.

- `sudo usermod -aG [groupname] [username]`  
  Adds a user to a group.

- `id [username]`  
  Shows user and group IDs.

- `who`  
  Displays who is logged on.

- `w`  
  Displays who is logged on and what they are doing.

- `last`  
  Shows a list of last logged in users.

[Back to Top](#table-of-contents)

---

## 14. SSH Commands

- `ssh-keygen`  
  Generates an SSH key pair.

- `ssh-copy-id [user]@[host]`  
  Copies SSH key to a remote host.

- `ssh-agent bash`  
  Starts a new shell with ssh-agent.

- `ssh-add [keyfile]`  
  Adds a private key to ssh-agent.

- `scp [user]@[host]:[source] [destination]`  
  Copies files from remote to local.

- `scp [source] [user]@[host]:[destination]`  
  Copies files from local to remote.

[Back to Top](#table-of-contents)

---

## 15. Miscellaneous Commands

- `alias [name]='[command]'`  
  Creates a shortcut for a command.

- `unalias [name]`  
  Removes an alias.

- `history`  
  Displays the command history.

- `sudo [command]`  
  Executes a command as the superuser.

- `sudo su`  
  Switches to the superuser account.

- `crontab -e`  
  Edits the cron jobs for scheduled tasks.

- `env`  
  Prints environment variables.

- `export [variable]=[value]`  
  Sets an environment variable.

- `screen`  
  Starts a new terminal session that can be detached from and reattached to.

- `tmux`  
  Terminal multiplexer.

- `chmod +x [file]`  
  Makes a file executable.

- `time [command]`  
  Measures the execution time of a command.

- `telnet [host] [port]`  
  Connects to a host over TCP.

[Back to Top](#table-of-contents)

---

## 16. Keyboard Shortcuts

- `Ctrl + C`  
  Terminates the current process.

- `Ctrl + Z`  
  Suspends the current process.

- `Ctrl + D`  
  Sends EOF or logs out of the current session.

- `Ctrl + L`  
  Clears the terminal screen.

- `Ctrl + A`  
  Moves the cursor to the beginning of the line.

- `Ctrl + E`  
  Moves the cursor to the end of the line.

- `Ctrl + R`  
  Searches the command history.

- `Ctrl + W`  
  Deletes the word before the cursor.

- `Ctrl + U`  
  Deletes from the cursor to the beginning of the line.

- `Ctrl + K`  
  Deletes from the cursor to the end of the line.

- `Tab`  
  Auto-completes file or command names.

[Back to Top](#table-of-contents)

---

## 17. Environment Variables

- `$HOME`  
  The current user's home directory.

- `$PATH`  
  Directories where the shell looks for commands.

- `$USER`  
  The current logged-in username.

- `$SHELL`  
  Path to the current shell.

- `$PWD`  
  The current working directory.

- `$EDITOR`  
  The default text editor.

- `printenv`  
  Displays environment variables.

- `set`  
  Lists shell variables and functions.

- `unset [variable]`  
  Removes an environment variable.

[Back to Top](#table-of-contents)
