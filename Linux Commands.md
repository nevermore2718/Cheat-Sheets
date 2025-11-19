## Linux Commands
Essential commands for operating in the Linux environment.

## Shells and Environment
| Command | Description |
| ------- | ----------- |
| echo $SHELL | Display the current user's shell |
| env | Show current environment variables |
| set | Display all shell variables and functions |
| export VAR=value | Set an environment variable for child processes |
| alias ll='ls -la' | Create an alis (example: ll for ls-la |
| unalias ll | Remove an alias |
| which command | Show the path to an executable |
| type command | Display how the shell interprets a command (alias, function, builtin, or file) |

## File Management
| Command | Description |
| ------- | ----------- |
| * | Wildcard symbol for variable length, e.g., * .txt refers to all files with the TXT extension |
| ? | Wildcard symbol referring to a single character, e.g., Doc? .docx can refer to Doc1.docx, DocA.docx, etc. |
| ls | List the names of files and subfolders in the current directory. Options include -l, -a, -t which you may combine, e.g., -alt |
| ls -l | Also show details of each item displayed, such as user permissions and the time/date when the item was last modified |
| ls -a | Also display hidden files/folders. May be combined with ls -l to form ls -al. |
| ls -t | Sort the files/folders according to the last modified time/date, starting with the most recently modified item |
| ls X | List the files |
| stat file | Display detailed file metadata (permissions, timestamps, inode, size) |
| file name | Show the file type (binary, text, symlink, directory) |
| pwd | Display the path of the current working directory |
| realpath file | Print the absolute path of a file |
| basename path | Strip filename, leaving only the directory path |
| dirname path | Strip filename, info, leaving only the filename |
| readlink -f file | Show the actual target of a symbolic link |
| cd Y | Change directory to Y. Special instances of Y .-- current directory, .. -- parent directory |
| cd | To the $HOME directory |
| cd .. | Up one level to enclosing folder or parent directory |
| cd /etc | To the /etc directory |
| cmp A B | Compare two files A and B for sameness. No output if A and B are identical, outputs character and line number otherwise |
| diff A B | Compare two files A and B for differences. Outputs the difference |
| mkdir X | Make a new directory named X inside the current directory |
| mv A B | Move a file from path A to path B. Also used for renaming files. |
| cp A B | Copy a file from path a to path B. Usage similar to mv both in moving to a new directory and simultaneously renaming the file in its new location |
| cp -r Y Z | Recursively copy a directory Y and its contents to Z. If Z exists, copy source Y into it; otherwise, create Z and Y becomes its subdirectory with Y's contents |
| rm X | Remove (delete) X permanently |
| rm -r Y | Recusively delete a directory Y and its contents |
| rm -f X | Forcibly remove file X without prompts or confirmation |
| rm -rf Y | Forcibly remove directory Y and its contents recursively |
| rmdir Y | Remove a directory Y permanently, provided Y is empty |
| open X | Open X in its default program |
| open -e X | Opens X in the default text editor (maxOS: TextEdit)
| touch X | Create an empty file X or update the access and modification times of X |
| cat X | View contents of X |
| cat -b X | Also display line numbers as well |
| wc X | Display word count of X |
| head X | Display the first 10 lines of X. If more than a single file is specified, each file is preceded by a header consisting of the string "==> X <==" where "x" is the name of the file |
| head -n 4 X | Show the first 4 lines of X |
| tail X | Display the last (10, by default) lines of X. If more than a single file is specified, each file is preceded by a header consisting of the string "==> X <==" where "X" is the name of the file |
| tail -n +1 X | Display entire contents of the file(s) X specified, with header of respective file names |
| less | Read a file with forward and backward navigation. Often used with pipe |

## Printing
| Command | Description |
| ------- | ----------- |
| lp file | Print a file using the default printer |
| lpr file | Print a file (alternative command) |
| lpq | Show print queue status |
| lprm job-id | Remove a job from the print queue |

## Input/Output Redirection
| Command | Description |
| ------- | ----------- |
| echo TEXT | Display a line of TEXT or the contents of a variable |
| echo -e TEXT | Also interprets escape characters in TEXT, e.g., \n -> new line, \b -> backslash, \t -> tab |
| echo -n TEXT | Omits trailing newline of TEXT |
| tee file | Wrtie output to both standard output and a file simultaneously |
| cmd > file | Redirect output of a command cmd to a file "file". Overwrites pre-existing content of "file" |
| 2 > & 1 | Redirect standard error to standard output |
| cmd >& file | Redirect output of cmd to file. Overwrites pre-existing content of file. Suppresses the output of cmd |
| cmd > /dev/null | Suppress the output of cmd |
| cmd >> file | Append output of cmd to file |
| cmd < file | Read input of cmd from file |
| cmd <<< string | Input a text string to cmd |
| cmd 2> foo | Redirect error messages of cmd to foo |
| cmd &> file | Redirect output and error messages of cmd to file | 
| & | Run a command in the background |

## Search and Filter
| Command | Description |
| ------- | ----------- |
| grep -r patt /path/to/src | Search recursively (the target directory /path/to/src and its subdirectories) for a text pattern patt |
| grep -v patt X | Return lines in X not matching the specified patt |
| grep -l patt X | Write to standard output the names of files containing patt |
| grep -i patt X | Perform case-insenstive matching on X. Ignore the case of patt |
| grep -E | Use extended regular expressions for more complex searches |
| find | Find files |
| find /path/to/src -name "*.sh"| Find all files in /path/to/src matching the pattern "*.sh" in the file name |
| find /home - size +100M | Find all files in the /home directory larger than 100MB |
| locate name | Find files and directories by name |
| sort X | Arrange lines of text in X alphabetically or numerically |
| awk '{print $1, $2}' file | Extract and process fields from structured text |
| cut -d: -f1 /etc/passwd | Extract fields by delimiter |
| tr 'a-z' 'A-Z' | Translate characters (e.g., lowercase to uppercase) |
| uniq file | Filter out duplicate lines from sorted output | 

## Text Processing
| Command | Description |
| ------- | ----------- |
| wc -l file | Count lines in a file |
| cut -d: -f1 /etc/passwd | Extract fields from text (example: usernames from /etc/passwd |
| sort file | Sort lines in a file alphabetically or numerically |
| tr a-z A-Z | Translate or replace characters (example: convert lowercase to uppercase) |
| grep pattern file | Search for a pattern in a file |
| egrep pattern file | Use extended regex patterns |
| fgrep string file | Search for fixed string (faster than regex) |

## Archives
| Command | Description |
| ------- | ----------- |
| tar | Manipulate archives with .tar extension |
| tar -v | Get verbose output while manipulating TAR archives. May combine this option with others, e.g., tar -tvf |
| tar -cf archive.tar Y | Create a TAR archive named archive.tar containing Y |
| tar -xf archive.tar | Extract the TAR archive named archive.tar | 
| tar -tf archive.tar | List contents of the TAR archive named archive.tar |
| tar -- exclude=pattern | Exclude files from an archive |
| zip -r Z.zip Y | Zip Y to the ZIP archive Z.zip |
| unzip Z.zip | Unzip Z.zip to the current directory |
| zip archive.zip files | Create a zip archive |

## File Transfer
| Command | Description |
| ------- | ----------- |
| ssh user@access | Connect to access as user |
| ssh access | Connect to access as your local username |
| ssh -p port user@access | Connect to access as user using port |
| ssh-copy-id user@host | Copy public key to a server for passwordless SSH login | 
| ssh -L local:remote:port user@host | Create a local port forwarding tunnel over SSH |
| scp -C file user@host:/path | Copy files over SSH with compression |
| sftp [user@] access | Login to access as user via secure file transfer protocol. If user is not specified, your local username will be used. |
| sftp access | Connect to access as your local username | 
| sftp -P port user@access | Connect to access as user using port |
| wget url | Download a file from the web | 
| curl -O url | Download a file keeping original filename |
| curl -L url | Follow redirects when downloading | 

## File Permissions
| Command | Description |
| ------- | ----------- |
| chmod permission file | Change permissions of a file or directory. Permissions may be of the form [u/g/o/a] [+/-/=] [r/w/x] or a three-digit octal number |
| chown user2 file | Change the owner of a file to user2 |
| chgrp group2 file | Change the group of a file group2 |
| chmod u+x file | Add execute permission for the owner |
| chmod g-w file | Remove write permission for group |
| chmod o=r file | Set others to read-only |
| unmask 022 | Show or set default permissions for new files | 
| getfacl file | View Access Control Lists on a file | 

## Numeric Representation
The table below compares Linux file permissions in octal form and in the format
| Octal | Permissions | Equivalent to Application of |
| ------- | ----------- | ------- |
| 0 | No permissions | -rwx |
| 1 | Execute permission only | =x |
| 2 | Write permission only | =w |
| 3 | Write and execute permission only: 2 + 1 = 3 | =wx |
| 4 | Read permission only | =r |
| 5 | Read and execute permission only: 4 + 1 + 5 | =rx |
| 6 | Read and write permissions only: 4 + 2 = 6 | =rw | 
| 7 | All permissions: 4 + 2 + 1 = 7 | =rwx |
| 644 | rw-r--r-- | Typical default for files |
| 755 | rwxr-xr-x | Typical default for directories and executables |
| unmask 022 | - | Default new files get 644 |
| unmask 027 | - | Default new files get 640 |

## Special Permission Bits
SUID (Set User ID): When set on an executable file, the program runs with the permissions of the file's owner instead of the user running it. Example: /usr/bin/passwd.
* Appears on the user/owner execute bit.
* s = SUID + execute
* S = SUID without execute
* Example : -rwsr-xr-x -> SUID set, owner can execute.

Example: -rwSr-xr-x -> SUID set, owner cannot execute.

SGID (Set Group ID): On executables, runs with the group's permissions. On directories, new files inherit the group of the directory instead of the creating user's group.
* Appears on the group execute bit.
* s = SGIC + execute
* S = SGID without execute
* Example: -rwxr-sr-x -> SGID set, group can execute.
* Example: -rwxr-Sr-x -> SGID set, group cannot execute.

Sticky Bit: On directories (like/tmp), users only delete or rename their own files, even if others have wrtie access to the directory.
* Appears on the others execute bit.
* t = sticky + execute
* T = sticky without execute
* Example: drwxrwxrwt -> world-writable directory with sticky bit (like.tmp).
* Example: drwxrwxrwT -> sticky set, others cannot execute.

### Octal permissions are 4 digits:
[special][user][group][others]

Special digit (first one):
* 4 = SUID
* 2 = SGID
* 1 = Sticky
* Add them together if you want more than one (e.g., 6 = SUID + SGID, 7 = SUID + SGID + Sticky)

| Octal | Special Bit | Placement | With Execute | Without Execute |
| ----- | ----- | ----- | ---- | ---- | 
| 4xxx | SUID | User Execute | rwsr-xr-x | -rwSr-xr-x |
| 2xxx | SGID | Group Execute | rwxr-sr-x | rwxr-Sr-x |
| 1xxx | Sticky | Others Execute | drwxrwxrwt | drwxrwxrwT |

## System Information
Commands handy for developing new applications for Linux or troubleshooting your Linux machine.

### General
Provide information about your Linux machine and perform administrative tasks.

| Command | Description |
| ------- | ----------- |
| uname | Show the Linux system information |
| uname -a | Detailed Linux system information |
| uname -r | Kernal release information, such as kernel version |
| uptime | Show how long the system's is running and load information | 
| su, sudo | Superuser; use this before a command that requires root access e.g., su shutdown |
| cal | Show calendar where the current data is highlighted |
| date | Show the current date and time of the machine |
| halt | Stop the system immediately |
| shudown | Shut down the system | 
| reboot | Restart the system |
| last reboot | Show reboot history |
| man COMMAND | Shows the manual for a given COMMAND. To exit the manual, press "q" |
| hostname | Show system host name |
| hostname -I | Display IP address of host |
| cat /etc/*- release | Show the version of the Linux distribution installed. For example, if you're using Red Hat Linux, you may replace * with readhat. |
| hostnamectl | Show or set the system hostname |
| timedatectl | Show or set date, time, and NTP |
| localectl | Show or set locale and keyboard layout |
| who | Show who is logged in |
| journalctl -b | Display logs since last boot |
| uptime -p | Show uptime in human-readable form |
| date | Show the current date and time of the machine |

## Hardware
Commands provide details about the hardware supporting your Linux machine.

| Command | Description |
| ------- | ----------- |
| dmesg | Display messages in kernal ring buffer (data structure that records messages related to the operation of the program running the operating system) |
| cat /proc/cpuinfo | Display information about the central processing unti (CPU) |
| cat /proc/meminfo | Display memory information |
| lspci -tv | Displays information about each Peripheral Component Interconnect (PCI) device on your system. The option -t outputs the information as a tree diagram, and -v is for verbose output |
| lsusb -tv | Display information about Universal Serial Bus (USB) devices and the devices connected to them. The option -t outputs the information as a tree diagram, and -v is for verbose output |
| dmidecode | Display system hardware components, serial numbers, and BIOS version |
| hdparm -i /dev/sda | Display information about the disk sda |
| hdparm -tT /dev/sda | Perform a read speed test on the disk sda |
| badblocks -s /dev/sda | Test for unreadable blocks on the disk sda |
| lsblk | List block devices and mount points |
| blkid | Show UUIDs and filesystem types |
| lsscsi | Display SCSI/SATA/NVMe devices |
| lsmod | List loaded kernel modules |
| modinfo module | Show details about a kernel module |
| modprobe module | Load a kernel module |
| rmmod module | Remoe a kernel module |
| sensors | Show temperature/voltage/fan readings |
| ls /dev | List device files |
| ls -l /dev/null/dev/zero | Display details of special device files |
| mount device dir | Mount a device (Example: mount/dev/sda1/mnt |
| unmount dir | Unmount a device |
| cat /etc/fstab | Show static filesystem mount configuration |

## Disk Usage
Commands that provide storage details

| Command | Description |
| ------- | ----------- |
| df | Display free disk space |
| df -T | Show filesystem type along with disk usage |
| du | Show file/folder sizes on disk |
| du -ah | Disk usage in human readable format (KB, MB, etc |
| du -sh | Total disk usage of the current directory |
| du -h | Free and used space on mounted filesystem |
| du -i | Free and used inodes on mounted filesystems |
| du --max-depth=1 -h | Show disk usage per directory |
| fdisk -l | List disk partitions, sizes, and types |
| parted -l | List partitions and details (alternative to fdisk |
| tune2fs -l /dev/sdX | Check and repair ext filesystems |
| e2fsck /dev/sdX | Check and repair ext filesystems |
| xfs_info /mountpoint | Display XFS fileystem information |
| mount /dev/sdX/mnt | Mount a filesystem |
| unmount /mnt | Unmount a fileystem |
| free -h | Display free and used memory in human readable units |
| free -m | Display free and used memory in MB |
| free -g | Display free and used memory in GB |
| swapoff / swapon | Disable or enable swap |

## Process Management and Performace Monitoring
Reminiscent of functions in Windows Task Manager, but on the command line.

| Command | Description |
| ------- | ----------- |
| & | Add this character to the end of a command/process to run it in the background |
| ps | Show process status |
| ps -e, ps -A | Either of these two commands prints all running processes in the system |
| ps -ef | Print detailed overview |
| ps -U root -u root | Display only the columns pid, user and command in ps output |
| ps -eo pid, user, command | Display only the columns pid, user and command in ps output |
| top | Display sorted information about processes |
| htop | Display sorted information about processes with visual highlights. It allows you to scroll vertically and horizontally, so you can see every process running on your system and entire commands |
| atop | Display detailed information about processes and hardware |
| kill PID | Kill a process specified by its process ID PID, which you obtain using the ps command |
| killall proc1 | Kill all processes containing proc1 in their names |
| lsof | List all open files on system. (This command helps you pinpoint what files and processes are preventing you from successfully ejecting an external drive.) |
| lsof -u root | List all files on the system opened by the root user. |
| mpstat 1 | Display processor-realted statistics, updated every second (hence the 1, whereas mpstat 2 refreshes the output every 2 seconds) | 
| vmstat 1 | Display virtual memory statistics (information about memory, system proccesses, pagging, interrupts, block I/O, disk, and CPU scheduling), updated every (1) second |
| iostat 1 | Display system input/output statistics for devices and partitions, virtual memory statistics, updated every (1) second |
| tail -n 100 /var/log/messages | Display the last 100 lines in the system logs. |
| tcpdump -i eth0 | Capture and display all packets on interface eth0 |
| tcpdump -i eth0 port 80 | Monitor all traffic on interface eth0 port 80 (HTTP) |
| watch df -h | Execute df -h and show periodic updates. To exit, press Ctrl+C |
| jobs | List jobs running in the background |
| fg %1 | Bring job 1 to foreground |
| bg %1 | Resume job 1 in background |
| systemctl status service | Show service status |
| systemctl start/stop/enable/disable service | Start, stop, enable, or disable a service |
| journalctl -xe | View recent logs with errors |
| journalctl -u service | View logs for a specific service |
| nice -n 10 cmd | Run a command with adjusted scheduling priority |
| renice -n -5 -p PID | Change priority of a running process |
| sare -u l | Display CPU usage statistics (if installed) | 

## Job Control
Commands that help you manage background and foreground processes, suspend jobs, and switch between them.

| Command | Description |
| ------- | ----------- |
| jobs | List background and suspended jobs |
| bg %1 | Resume job 1 in the background |
| fg %1 | Bring job 1 to the foreground |
| Ctrl+Z | Suspend the current foreground process |

## User Management
Commands that give information on the system's users and allows superuser administrators to change user settings.

| Command | Description |
| ------- | ----------- |
| who | Display who is logged in |
| w | Display what users are online and what they are doing |
| users | List current users |
| whoami | Display what user you are logged in as |
| id | Display the user ID and group IDs of your current user |
| last | Display the last users who have logged onto the system |
| groupadd gp1 | Create a group named gp1 |
| useradd -c "Alice Bob" -m abl | Create an account named ab1, with a comment of "Alice Bob" and create the new user's home directory |
| userdel ab1 | Delete the account named ab1 |
| usermod -aG gp1 ab1 | Add the account ab1 to group gp1 |
| passwd user | Set or change a user's password |
| passwd -l user | Lock a user account |
| passwd -u user | Unlock a user account | 
| chage -l user | Display account password expiry info |
| chage -M 90 user | Set password to expire every 90 days |
| /etc/login.defs | File that sets user defaults (e.g., password aging) |
| /etc/skel | Default files copied to new user's home |
| /etc/passwd | Stores password hashes and aging info |
| /etc/shadow | Stores password hashes and aging info |
| /etc/group | Stores group definitions |
| su - user | Switch to another user with the environment |
| sudo -i | Start a root login shell |
| groups user | Show groups the user belongs to |

## Networking
Commands to regulate how your Linux machine communicates with other computers, such as the local area network (LAN) router or external websites

| Command | Description |
| ------- | ----------- |
| ifconfig | Display all network interfacees with IP addresses |
| ifconfig -a | Display all network interfaces, even if any of them is down, with IP addresses |
| ifconfig eth0 | Display IP addresses and details of the eth0 interface |
| ip a | Another way to display all network interfaces with iP
| ethtool eth0 | Query or control network driver and hardware settings of the interface eth0 |
| netstat | Print open sockets of network connections, routing tables, interace statistics, masquerade connections, and multicast memeberships. |
| netstat -a | Show both listening and non-listening sockets |
| netstat -l | Show only listening sockets |
| netstat -nutlp | Show listening TCP and UDP ports and corresponding programs | 
| ping host | Send ICMP echo requet to host, which may be a symbolic name, domain name or IP address |
| whois domain | Display information for domain |
| dig domain | Display DNS information for domain |
| dig -x addr | Do a reverse lookup on an IPv4 or IPv6 address addr |
| host domain | Display DNS IP address for domain
| wget LINK | Download from location LINK |
| curl LINK | Display the HTML source of LINK.|
| ip link show | Show network interfaces (modern replacement for ifconfig) |
| ss -tullwn | Show listening TCP/UPD ports (modern replacement for netstat) |
| nmcli | Manage network connections via NetworkManager |
| ip route | Show routing table |
| traceroute host | Trace route packets take to a host |
| mtr host | Continuous tracerote + ping statistics |
| nslookup host | Query DNS (legacy tool, still tested) | 
| /etc/resolv.conf | File containing DNS server config |
| nmap -sT host | Scan open TCP ports (basic knowledge expected ) |
| firewall-cmd -- list-all | Show firewalld configuration |
| ufw status | Show uncomplicated firewall status |

## Containers
Commands to assist with building and running Dockt images, manage active containers, and interact with Kubernetes pods for orchestration.

| Command | Description |
| ------- | ----------- |
| docker run -it image | Run a container interactively |
| docker build -t name | Build an image from a Dockerfile |
| docket ps | List running containers |
| docker exec -it id bash | Get a shell inside a running container |
| docker stop id | Stop a container |
| docker rmi image | Remove an image |
| kubectl get pods | List Kubernetes pods |
| kubectl describe pod name | Show pod details |

## Scripting and Automation
Commands that cover shell loops, conditionals, scheduling tasks, and version control with Git to automate workflows

| Command | Description |
| ------- | ----------- |
| for var in list; do ...; done | Loop through a list of values |
| while condition; do ...; done | Loop while a condition is true |
| if [ condition ]; then ...; fi | Conditional execution |
| read var | Read input into a variable |
| echo $var | Output variable contents |
| $? | Show exit status of last command |
| cron / crontab -e | Schedule recurring tasks |
| at time | Schedule a one-time task |
| git clone url | Clone a Git repo |
| git add file | Stage file changes |
| git commit -m "msg" | Commit changes |
| git push | Push commits to remote repo |
| git checkout branch | Switch to a branch |
