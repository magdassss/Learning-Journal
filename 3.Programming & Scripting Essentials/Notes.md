## 3.1 Linux for Data Engineers

### Objectives
- Where and why Linux is used
- How Linux works
- Practical Linux lab

**1. Difference between macOS, Windows, and Linux**

**macOS**
- Proprietary
- User-friendly
- Integration
- Security

**Windows**
- Proprietary
- Broad user base
- Historically reactive
- Security

**Linux**
- Open source
- User freedom
- Customisation
- Community-driven

**2. Introduction to Linux**

➢ Created by Linus Torvalds in 1991
➢ Unix based
➢ First version released in 1994
➢ FOSS (Free and Open Source Software)
➢ Can be modified as long as the source code is shared.
➢ Contains so called GNU Utilities, compatible with Unix (gnu.org)

**3. Linux distros**
- The distros share the same Linux kernel (core system) 
- Open-source code allows for easy bug review and fast issue resolution
- The distros share the same access model. Clear distinction between regular users and root enhances security.
- sudo grants temporary privileges, reducing accidental changes
- The distros provide standard network protection tools, filesystem tools, scripting toole, etc.
- All Linux distros are less targeted by malware than Windows. These makes them a great choice for server software

**4. Linux file system**
- The Directory Structure in Unix & Linux is a unified Directory Structure
- All the directories are unified under the “/” Root file system
- This structure is maintained irrespective of where the File System is physically mounted. It is an abstraction.
- All the directories are arranged hierarchically under the Root file system

- in Linux everything as a file e.g. memory, device-drivers, named pipes, and other system resources
- hence why filesystem security is so important
- I/O to devices is via a “special” file
- e.g. /dev/cdrom
- have other special files like named pipes
- a conduit between processes / programs

**Directory is a special type of file**
**Directories contain subdirectories**

**5. Special filesystem directories**
- /etc - Configuration Files
- /dev – Devices
- /tmp – Temporary Files
- /mnt – Mount Directory
- /lib System libraries
- /lib64 System libraries (64bit)
- /lost+found Used by system to store recovered files after file systems check has been performed
- /proc Provides info about running processes

**/bin – User Binaries**
- Contains binary executables.
- Common linux commands you need to use in single-user modes are located under this directory.
- For example: ps, ls, ping, grep, cp.

**/sbin – System Binaries**
- Just like /bin, /sbin also contains binary executables.
- But, the linux commands located under this directory are used
typically by system administrator, for system maintenance purpose.
- For example: iptables, reboot, fdisk, ifconfig

**/var – Variable Files**
- var stands for variable files.
- Content of the files that are expected to grow can be found under this directory.
- This includes — system log files (/var/log); packages and database files (/var/lib); emails (/var/mail); print queues (/var/spool); lock files (/var/lock); temp files needed across reboots (/var/tmp);

**/usr vs /home**
- In the original Unix implementations, /usr was where the home directories of the users were placed (that is to say, /usr/someone
was then the directory now known as /home/someone).
- Currently, /usr is where user-land programs and data (as opposed to 'system land' programs and data) are. The name hasn't changed,
but it's meaning has narrowed and lengthened from "everything user related" to "user system resources”
- /home is for home directories for all users to store personal files.

**/boot – Boot Loader Files**
- Contains boot loader related files
- Grub files are located under /boot
- For example: initrd.img-2.6.32-24-generic, vmlinuz-2.6.32-24- generic

**/opt – Optional add-on Applications**
- opt stands for optional.
- Contains add-on applications from individual vendors.
- add-on applications should be installed under either /opt/ or /opt/ sub-directory

**6. Understanding Linux**

**File or directory Details**
**Home directories** /root, /home, /username
**User executables** /bin, /usr/bin, /usr/local/bin
**System executables** /sbin, /usr/sbin, /usr/local/sbin
**Other Mountpoints** /media, /mnt
**Configuration** /etc
**Temporary Files** /tmp
**Kernels and Bootloader** /boot
**Server Data** /var, /srv
**System Information** /proc, /sys
**Shared Libraries** /lib, /usr/lib, /usr/local/lib

**7. How Linux works**

- Two types of login screens
- virtual consoles (text-based)
- graphical logins (display managers)
- Login using login name and password
- Each user has a home directory for personal file storage

 **Shell Prompt**
 - Once a shell is started
a) Initialisation
b) Waiting for command
- Prompt gives useful information

**Superuser, root**
- Root is all powerful* ( do not leave this account open)
- Similar to administrator account on Windows
- Normal user accounts can only do a subset of the functions root can do.
- Root access may be required to:
A) Install programs
B) Start/ stop an application
C) Change/ access configuration files

**Running As Unprivileged User/Group**
- every process “runs as” some user
- extremely important this user is not root
- since any bug can compromise entire system
- may need root privileges, e.g. bind port
- have root parent perform privileged function
- but main service from unprivileged child
- user/group used should be dedicated
- easier to identify source of log messages

**8. Linux security model**
- people or proceses with “root” privileges can do anything
- other accounts can do much less
- hence attacker’s want to get root privileges
- can run robust, secure Linux systems
- crux of problem is use of Discretionary Access Controls (DAC)

**File permissions**
- files have two owners: a user & a group
- each with its own set of permissions
- with a third set of permissions for other
- permissions are to read/write/execute and set in this order: user group other
- set using chmod command

**9. Users and groups**
- user's details are kept in /etc/password
- See additional group details in /etc/group “pianists:x:102:maestro,volodya”
- use useradd, usermod, userdel to alter

**10. Linux commands**
- ls – list directory contents
- cd – change the current directory
- pwd – display the present working directory
- cat – concatenates and display files
- echo – Display arguments to the screen.
- man – Display the online manual
- exit – Exits the shell or your current session
- clear – Clears the screen
- cd, change directory
- cd ..
- cd –
- cd ~/mydir
- cd /home/usman
- cd
- su, switch user, su – (complete user environment)
- passwd, change password


## 3.2 Version Control

### Objectives
- Understand the principles of DevOps and its application in data
engineering to enhance collaboration, automation, and monitoring
- Gain practical knowledge of version control, Continuous Integration
and Continuous Deployment (CI/CD) processes to ensure efficient
and reliable delivery of data products
- Conduct effective code reviews using GitHub to maintain code
quality and facilitate team collaboration

- An introduction to version control
- Git and its applications
- Practical demonstration - Working with repositories
- Git branching, changes and merges

**1. Introduction to version control**
- Version control keeps record of your changes in codes
- Allows you to revert any changes and go back to a previous state
- It's a time machine

**2. Different version control types**
- local VCS
- central SVN
- distributed - Git

**3. Introducing Git**
- Free and open-source version control system
- Created by Linus Torvalds in 2005
- Widely used, fast, and offline-capable
- Efficient storage of file changes
- Good at merging code versions
- Enables easy code exchange and backup

- Git solves data engineering problems related to collaboration and reproducibility
- Git has simple – yet powerful – concepts
- Multiple services available for it

**4. Git vs. OneDrive/Dropbox**
- Git works similarly, but with more control/ at each step

**5. Point-and-click interfaces**
Some coding environments come with Git integration, e.g.
- RStudio
- PyCharm
- VSCode

**6. GitLab / GitHub** 
- These are different websites but both tools are built on top of Git
- You can think of them as online storage of Git repositories
- Repository management that acts as your single source of truth in a distributed version control workflow
- These also includes code review tools with tons of collaboration and flow management features
- Both also have an issue tracker with issue boards and a project wiki.

**7. Git workflow**
- create branch
- start with clean working directory
- make some changes
- create a snapshot - create commit
- make a commit
- pull and push to repository

**8. The three states of Git**
- modified: files are changed but have not been committed it to your database yet
- staged: modified file in its current version is marked to go into your next commit
- committed: data is safely stored in your local database

**9. Working with repositories**
- NEVER place a git repository in e.g. OneDrive
- NEVER place a git repository inside another git repository
- Don’t get lazy with commit messages!
- For code that other people will use, use Semantic - Versioning for version numbers - Major.Minor.Patch

- Use branching in GitHub for group projects
- Branches are deviations in the commit tree
- Branches are useful for feature management
- Be aware of merge conflicts

**10. Branching**

What is a branch?
- git branch - lists all the branches in your repo and show your current branch
- git checkout –b <branchname> - creates a new branch and switch to it
- git checkout <branchname> - switch from one branch to another
- git merge <branchname1> <branchname2> - adds a file to the staging area

- Concept to make changes, without affecting the master-version
- Multiple branches can co-exist in parallel
- Used to implement new features
- Can be merged into each other

**11. Git functionalities**
1. Branches and Merging
2. HEAD
3. Reversing changes
   

## 4.1 Linux for Data Engineers

### Objectives

- Identify the main approaches to software development
- Apply variables and common operators in Python
- Explain software testing and test-driven development

**1. The SLDC model**
- Planning
- Analysis
- Design
- Development
- Testing
- Deployment
- Maintenenace

**2. Agile SDLCs**
- Speed up or bypass one or more life cycle phases
- Usually less formal and reduced scope
- Used for time-critical applications
- Used in organisations that employ disciplined methods

Agile development frequently uses iterative development or incremental delivery (or both).

**3. XP - eXtreme Programming**
- For small-to-medium-sized teams developing software with vague or rapidly changing requirements
- Coding is the key activity throughout a software project
- Communication among teammates is done with code
- Life cycle and behavior of complex objects defined in test cases – again in code

*Best Practises*
- Code reviews: Review code all the time
- Testing: Everybody tests all the time
- Simplicity: Maintain simplest design for current functionality
- Design: Everybody designs daily
- Architecture: Everybody refines the architecture
- Integration Testing: Build and integrate tests several times a day
- Short Iterations: Keep iterations extremely short

**4. Syntax vs semantics**
Semantics - meaning of your program
Syntax - specifying your algorithm using a programming language

**5. Python and types**
- Dynamic typing: Python determines the data types of variable bindings in a program
automatically
- Strong typing: But Python’s not casual about types, it enforces the types of objects

**6. Lists, Dictionaries, tuples**
- list []- unordered collection of elements
- dictionary {} - unordered collection of data (key value pairs)
- tuples () - immutable - cannot be changed unless we re-assign value points

**7. Type conversions**
x = 10
x_int = int(x)
        float(x)
        complex(x)

**8. Strings**

**9. Indexing**

**10. Booleans**

**11. Conditional statetements & Loops**
