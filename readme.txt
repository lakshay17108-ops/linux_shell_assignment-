Step 1- Installation
 Option B — Install Ubuntu  on Windows 10/11 Prerequisites: Windows 10 or Windows 11
PowerShell (Admin) access. 
Steps (PowerShell/Command Prompt as Administrator) 1
Enable oracle virtual box and Virtual Machine Platform features: 
oracle virtual box--install 
(This installs oracle virtual box and will install a default Linux distribution (usually Ubuntu))
run: vm--update vm--set-default-version 2
 Install Ubuntu from Microsoft Store: search "Ubuntu" and click Install (e.g., Ubuntu 22.04 LTS ).
 Launch Ubuntu from Start Menu → set username and password. Screenshots to capture: - PowerShell command running 
vm--install (show success message) 
vm--install
 vm--update
 Hardware Configuration
 vm example - Host OS:
 Windows 11 - vm version : vm 7.2.4 
Ubuntu distro: Ubuntu 22.04 LTS 
Memory/ disk: vm uses host resources
Step 2 — Shell command implementations and documentation
 A) File Navigation
 1) pwd
 Syntax: pwd
 Description: Print working directory — shows current directory path
When/Why: Use to confirm your current directory before running file operations
 2 ) ls 
Syntax: ls
 Description: List directory contents
 When/Why: Quick view of files; use( -l for long format, -a to include hidden files)
3) Cd
 Syntax: cd [directory] 
Description: Change directory
When/Why: Navigate filesystem to the folder where you want to operate
4) tree 
Syntax: tree [options] [directory] 
Description: Display directory tree (hierarchical) 
When/Why: Visualize directory structure — useful for documentation and debugging. (If tree is missing: sudo apt update && sudo apt install tree .)
 B) File and Directory Management
 1) mkdir
 Syntax: mkdir [options] directory_name
 Description: Create a directory
When/Why: Create directories to organize files
2)touch 
Syntax: touch filename
 Description: Create an empty file or update timestamp 
When/Why: Quickly create placeholder files
 3) cp 
Syntax: cp [options] source destination
 Description: Copy files or directories ( -r for recursive)
When/Why: Duplicate files or folder trees
4) mv 
Syntax: mv [options] source destination 
Description: Move or rename files/directories
When/Why: Organize or rename items
5) rm 
Syntax: rm [options] file 
Description: Remove files. Use (-r to remove directories recursively and -f to force)
When/Why: Delete unnecessary files. Be careful — deletions are permanent
C) Permissions Management 
1) chmod
 Syntax: chmod [options] 
Description: Change file mode (permissions)
 When/Why: Secure files by restricting write/execute permissions
2) chown
 Syntax: chown [owner][:group] file
 Description: Change file owner and/or group
When/Why: Set correct ownership for scripts or service files
D) Process Monitoring 
1)  ps
 Syntax: ps [options] 
Description: Report snapshot of current processes. Common: (ps aux )
 When/Why: Check running processes, PIDs for troubleshooting
 2)  top 
Syntax: top 
Description: Interactive process viewer with CPU/memory usage
 When/Why: Monitor system in real-time; kill misbehaving processes
 3) kill 
Syntax: kill [signal] PID or kill -9 PID 
Description: Send signals to processes (terminate, etc.)
When/Why: Stop misbehaving processes when graceful shutdown fails
E) Networking Tools 
1) Ping
 Syntax: ping [options] destination 
Description: Send ICMP echo requests to check reachability and latency. When/Why: Basic network connectivity test
 2)  Ifconfig / ip
 Syntax: ifconfig or ip addr show 
Description: Show network interface configuration. ( ifconfig may be deprecated in favor of ip .) 
When/Why: See assigned IPs and interface states
 3) netstat (or ss ) 
Syntax: netstat -tuln or ss -tuln
 Description: List network sockets and listening ports
 When/Why: Debug network services and port conflicts
Step 3 — Shell scripts
 • Script A — Backup a Directory ( backup_dir.sh )
 Explanation & usage: - The script accepts two arguments — the source path and a backup root directory. - It creates a timestamped backup directory and uses cp -a to preserve permissions and symbolic links. 
• Script B — CPU/Memory Monitoring ( resource_monitor.sh ) 
• Script C — Automated Download Task ( auto_downl
