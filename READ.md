 Course: Introduction to Linux
Tutor: Johnson
Date: Jan 25, 2025
Duration: 3 Hours

Installing Linux (Recommended Ubuntu)
Macbook and Higher Window Version users can use: Multipass
https://canonical.com/multipass/install
After the installation, run the command:
multipass shell <nameofyourinstance>
change the password by running:
sudo passwd ubuntu


Use can also borrow a vm from Amazon

For you to connect to your virtual server or machine, you need to have an SSH client.
In this course, we are using Visual Studio Code. You can also use Putty or Windows Terminal.

Download Visual Studio Code from: https://code.visualstudio.com/download

For beautifying your terminal, you can install Oh My Zsh: https://ohmyz.sh/

# 1. Introduction to Linux
- What is Linux?
An open-source operating system based on the Unix architecture.
Popular distributions (distros) include Ubuntu, RedHat, Debian, Fedora, CentOS, etc.
Community-driven, stable, secure, and widely used in data centers, cloud infrastructure, 
  and development environments.

- Why Linux for Data Analytics?
Powerful command-line tools for data manipulation and automation.
Rich ecosystem for open-source data analytics tools (Python, R, Jupyter, etc.).
Easily scriptable environment for ETL (Extract, Transform, Load) tasks.
Resource-efficient for server deployments.

- Linux Architecture
Kernel: The core managing hardware resources and processes.
Shell: Interface between user and kernel (e.g., Bash, Zsh).
File System: Hierarchical structure, everything is a file.
Utilities: Basic command-line tools and system programs.

# 2. Basic Command-Line (CLI) Usage

Accessing the Server:
Typically via SSH (Secure Shell).
On Windows, use PuTTY or Windows Terminal with ssh.
On macOS/Linux, open Terminal and type ssh username@server_ip.

ssh -i "name of your keypair with .pem extension" ubuntu@server_public_ip

eg: ssh -i "jomacs-ia-wn-key.pem" ubuntu@54.187.178.22

Command Structure
Syntax: command [options] [arguments]
Example: ls -l /home
ls is the command
-l is an option (long listing format)
/home is an argument (the directory to list)

touch command: Used to create a new file
Syntax: touch filename.txt

File extensions:
.txt: Text file
.sh: Shell script
.py: Python script
.csv: Comma-separated values
.ipynb: Jupyter Notebook
.json: JavaScript Object Notation
.yml: YAML file

Creating a folder: mkdir directory_name

Useful Keyboard Shortcuts
Ctrl + C: Terminate the current process.
Ctrl + Z: Send current process to the background (suspend).
Ctrl + R: Reverse search through command history.
Tab: Auto-completion for commands, files, directories.

Common Commands
- pwd (Print Working Directory): Shows your current directory path.

- ls (List): Lists files in a directory.
Common options:
ll (for long listing)
ls -l (long listing)
ls -a (show hidden files)
ls -lh (human-readable file sizes)

- cd (Change Directory): Navigate between directories.
cd ~ (go to the home directory)
cd .. (go up one directory level)

King George V 
Queen Elizabeth II
Prince Charles
Prince William
Prince George 

- mkdir (Make Directory): Create directories.

- touch (Create Empty File): Creates an empty file or updates file timestamps.

- rm (Remove Files/Directories):
rm file.txt
rm -r directory/ (recursively remove directory)
rm -i file.txt (prompt before removal)

Assignment: 
- Sign up GitHub before you come to class 
Url: https://github.com/



Course: Introduction to Linux
Tutor: Johnson
Date: Jan 26, 2025
Duration: 3 Hours


- cp (Copy Files):
cp file.txt /path/to/destination/

- mv (Move/Rename Files):
mv old_file.txt new_file.txt (rename a file)

- echo (Output Text):
echo "Hello, World!"

- append text to a file
echo "Hello, World!" >> file.txt

- overwriting a file
echo "Hello, World!" > file.txt

- cat (Concatenate or Display File Content):
cat file.txt

- less (View File Content in Pages):
less file.txt

SELECT TOP 10 * FROM table_name
WHERE location = 'Lagos'

Press q to quit.

- head / tail (View Beginning or End of File):
head -n 20 file.txt (first 20 lines)
tail -n 20 file.txt (last 20 lines)
tail -f file.txt (continuously follow appended data – useful for logs)
# 3. Linux File System and Directory Structure
- Hierarchy
Single root directory /, everything else resides under it.
Common folders:
/bin, /usr/bin: System-wide binaries and executables.
/etc: Configuration files. eg. cat etc/os-release
/home: User home directories.
/var: Variable files (logs, spool, etc.).
/tmp: Temporary files.
/opt: Optional software packages.
/root: Home directory of the root user (administrator).

Absolute vs. Relative Paths
- Absolute: Start from root /. Example: /home/data/file.csv.
- Relative: Start from current directory. Example: ../file.csv.

- File and Directory Permissions
Three types of permissions: read (r), write (w), execute (x).
Three categories of users: owner, group, others.
Permission notation: rwxr-xr--
Command to change permissions: chmod
Symbolic mode: chmod u+x file.sh (give execute permission to the owner)
Numeric mode: chmod 755 file.sh (owner: rwx, group: r-x, others: r-x)
Command to change ownership: chown
sudo chown username:groupname file.txt


# 4. Working with Text Editors
- Nano
Simple, user-friendly command-line editor.
nano file.txt
Common shortcuts:
Ctrl + O: Write out (save)
Ctrl + X: Exit
Ctrl + K: Cut line
Ctrl + U: Uncut (paste) line

- Vi/Vim
Powerful, modal editor.
Launch with vi file.txt or vim file.txt.
Modes:
Normal mode: Navigation, copy/paste, etc.
Insert mode: Text input. Enter with i.
Command mode: For saving, quitting, searching, etc. (press :).
- Common tasks:
Press i to insert.
Press Esc to exit insert mode.
:w to save. :q to quit. :wq to save and quit. :q! to force quit.

VSCode Server or Other Remote Editors
For advanced editing, you can install a remote development environment or use an SSH extension.



# 5. Managing Software Packages (Ubuntu)
- APT (Advanced Package Tool)
Main package manager on Ubuntu.
sudo apt update: Update package index.
sudo apt upgrade: Upgrade installed packages.
sudo apt install <package_name>: Install a package.
sudo apt remove <package_name>: Remove a package.
sudo apt search <keyword>: Search package repositories.
sudo apt autoremove: Remove unused dependencies.

- Snap
Containerized software packaging solution.
Example usage: sudo snap install <package_name>.

- Installing Tools Useful for Data Analysis
Python 3.x: Often pre-installed on Ubuntu. Otherwise sudo apt install python3.
pip: sudo apt install python3-pip.
R: sudo apt install r-base.
Jupyter Notebook: pip install jupyter.
Git: sudo apt install git.
Docker (optional but useful): Follow official documentation or sudo apt install docker.io.



# 6. Environment Variables and Shell Configuration
- Environment Variables
Variables that affect the processes and behavior of running applications.
Examples: PATH, HOME, USER, LANG.
To list environment variables: printenv or env.
To set a variable temporarily: export MY_VAR="Hello".
To make it permanent, add export MY_VAR="Hello" to ~/.bashrc or ~/.profile.

- Shell Configuration Files
~/.bashrc: Configuration file for interactive bash shells.
~/.profile or ~/.bash_profile (depending on distro/shell).
Common usage: alias definitions, environment variable exports, function definitions.
Example alias: alias ll='ls -la' (makes “ll” run “ls -la”).


# 7. Basic Networking and Remote Access
- IP Addresses and Hostnames
Check your server’s IP with ip addr show or hostname -I.
Hostname with hostname.

- Network Utilities
ping <host>: Check connectivity to a host.
curl <url> or wget <url>: Download data or make HTTP requests.
scp: Secure copy files between hosts.
Example: scp localfile.txt user@remotehost:/path/to/destination/

- SSH Key Authentication
Generate key pair: ssh-keygen -t rsa
Copy public key to server: ssh-copy-id user@server_ip
Enhanced security, no password required once set up.

# 8. Essential Data Manipulation Commands
- Data analysts often manipulate large CSV/text files, logs, or preprocess data before feeding into scripts. The following commands are powerful allies:
1. grep
Search for patterns in files.
Syntax: grep [options] "pattern" file(s)
Example: grep -i "error" server.log (case-insensitive search for “error”)

2. awk
Pattern scanning and processing language. Great for quick transformations.
Example: awk -F "," '{print $1, $3}' data.csv
Uses comma as field separator, prints first and third columns.

3. sed (Stream Editor)
Text transformations on the fly.
Example: sed 's/oldtext/newtext/g' file.txt (substitute “oldtext” with “newtext” globally in each line)

4. sort and uniq
sort file.txt: Sort lines alphabetically (or numerically with -n).
uniq: Remove or count duplicate lines. Often used together:
sort file.txt | uniq
sort file.txt | uniq -c (count occurrences of duplicates)

5. cut
Extract sections of lines from files.
Example: cut -d "," -f 1,3 data.csv (use comma as delimiter, extract fields 1 and 3).

6. paste
Merge lines of files side by side.
Example: paste file1.txt file2.txt

7. join
Join lines of two files based on a common field.

8. wc (Word Count)
wc file.txt: Returns number of lines, words, and bytes in file.
Options: -l (lines), -w (words), -c (bytes).

9. xargs
Build and execute command lines from standard input.
Example: grep -l "error" *.log | xargs rm (removes all .log files containing “error”)

\
# 9. Shell Scripting and Automation
- Why Shell Scripts?
--Automate repetitive tasks.
--Batch processing of data files.
--Scheduling with cron.

- Basic Script Structure
First line: #!/bin/bash (shebang to specify shell).
Make script executable: chmod +x script.sh
Run it: sudo ./script.sh

- Variables and Comments
name = "Johnson"
echo "Hello, $name!"



Example Automation Script 
#!/bin/bash
# A simple ETL script example

# 1. Extract data (download a file)
#    -O (uppercase 'O') tells wget where to save the file
wget -O /home/ubuntu/data.csv https://raw.githubusercontent.com/uiuc-cse/data-fa14/gh-pages/data/iris.csv

# 2. Transform data (clean using awk)
#    Keep the header (NR==1) or rows where sepal_length > 6.0 (the first column is $1).
awk -F "," 'NR==1 || $1 > 6.0 {print $0}' /home/ubuntu/data.csv > /home/ubuntu/data_clean.csv

# 3. Load data (move to a final directory)
#    Make sure the destination directory exists, then move the cleaned file there.
mkdir -p /home/ubuntu/data_analytics
mv /home/ubuntu/data_clean.csv /home/ubuntu/data_analytics/final_data.csv

echo "ETL process completed!"





# 10. Scheduling Tasks with Cron
- Cron Basics
Cron is a daemon for running tasks at scheduled times.
Use crontab -e to edit a user’s cron table.

- Cron Syntax
* * * * * <command_to_execute>
Five fields: minute, hour, day_of_month, month, day_of_week.
Example: 0 2 * * * /home/user/backup.sh (runs backup script every day at 2 AM).

- Common Schedules
*/5 * * * * /home/user/script.sh (every 5 minutes)
30 6 * * 1 /home/user/report.sh (every Monday at 6:30 AM)

- Logging and Troubleshooting
Cron logs often in /var/log/syslog on Ubuntu.
Make sure scripts have executable permissions and correct shebang.

# 11. Monitoring and Logging
- System Logs
Located in /var/log/.
Key logs: syslog, auth.log, etc.
Check logs with tail -f /var/log/syslog.

- Process Monitoring
top or htop: Interactive view of system processes.
ps aux: Detailed process listing.
kill <pid> or kill -9 <pid> if a process is stuck.

- Disk Usage
df -h: Show disk usage with human-readable format.
du -sh <directory>: Shows disk usage for a directory.

- Performance Monitoring
free -h: Check memory usage.
iostat, vmstat, netstat (installed via sysstat package sometimes).
12. Working with Python/R Environments (for Data Analytics)

- Python
-- Installing Python 3 and pip:
sudo apt update
sudo apt install python3 python3-pip

-- Creating a virtual environment:
python3 -m venv myenv
source myenv/bin/activate
pip install pandas numpy

-- Deactivating a virtual environment: deactivate

- R
-- Install R on Ubuntu:
sudo apt update
sudo apt install r-base
Run R console: R
-- Install packages inside R: install.packages("tidyverse").


- Jupyter Notebook
pip install jupyter
Start notebook: jupyter notebook --ip=0.0.0.0 --port=8888 --no-browser
Access via a browser: http://server_ip:8888 (with the token provided).



# 13. Version Control with Git

Install gitbash on your local machine if you want to run linux commands on your local machine.
https://git-scm.com/downloads/win

- Why Git?
Track changes, collaborate with team members, revert to previous versions of code.

- Installing Git
sudo apt install git

- Basic Usage
Initialize a repository: git init.
Check status: git status
Add files: git add file.py.
Commit changes: git commit -m "Initial commit".

View commit history: git log.

Connect to remote repo (e.g., GitHub/GitLab):
git remote add origin https://github.com/user/repo.git
git push -u origin main

- Branching
Create a branch: git checkout -b feature_branch.

- Merge back into main branch:
git checkout main
git merge feature_branch



# 14. Security and User Management
Root vs. Normal Users
Root user has administrative privileges.
Use sudo sparingly.
Adding a New User
sudo adduser datauser
sudo usermod -aG sudo datauser  # to grant sudo privileges


SSH Security
Disable root login in /etc/ssh/sshd_config by setting PermitRootLogin no.
Use SSH key-based authentication.


Firewall
Ubuntu comes with ufw (Uncomplicated Firewall).
sudo ufw allow ssh
sudo ufw allow 8888/tcp (to allow Jupyter Notebook port)
sudo ufw enable (enable firewall).

# Some Command Line Tricks:
1. Let's assume you're in your home directory then you: cd /etc 
   You can go back to your home directory by typing: cd - 

2. To repeat the last command you typed, you can type: !!

3. To clear screen, type and hold ctrl + l 

4. Type reset to reset the terminal

5. pushd and popd are used to navigate between directories. 
pushd saves the current directory and changes to the new directory. 
popd returns to the saved directory.






 # 15. Summary and Best Practices
- Keep your system updated (sudo apt update && sudo apt upgrade).
- Use version control for all data and scripts.
- Automate repetitive tasks with shell scripts and cron.
- Utilize environment management (virtualenv, conda) to isolate project dependencies.
- Monitor performance (CPU, memory, disk usage) on your server.
- Practice good security hygiene (key-based SSH, firewall, least privilege).
- Document your processes (in README files or wikis) for reproducibility.

Additional Learning Resources
Ubuntu Official Documentation: https://help.ubuntu.com/
GNU Bash Reference Manual: https://www.gnu.org/software/bash/manual/bash.html
Linux Journey: https://linuxjourney.com/ (free online Linux lessons)

Data Wrangling CLI Tools:
https://www.baeldung.com/linux/bash-data-science-basics (tutorials for grep, sed, awk, etc.)
Git Documentation: https://git-scm.com/doc
