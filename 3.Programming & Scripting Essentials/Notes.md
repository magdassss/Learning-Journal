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
   

## 3.3 Python for Data Engineers

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

**11. Conditional Statetements & Loops**


## 3.4 Object Oriented Programming

### Objectives
- Describe the key concepts of Object-Oriented Programming
(OOP) in Python
- Demonstrate knowledge of how to create classes, objects,
and methods in Python
- Describe advanced OOP concepts and their use-cases

**1. What is Object-Oriented Programming?**

OOP - a method of structuring a program by bundling related properties and behaviours into individual objects.
- Simplifies code
- Models real world
- Encapsulation protects data
- Makes complex systems managable
- Modular

- reusability
- organisation
- enhanced data security

**2. OOP in python**
Object-oriented Programming is an approach for modelling concrete, real-world things, like cars, as
well as relations between things, like companies and employees, students and teachers, and so on.

**3. Defining a Class in OOP**
- you can think of a class as a blueprint for creating objects
- classes provide a way to create objects
- fundamental concept of OOP and allow for the creation of complex applications by modelling real-world objects or concepts

**4. Objects in OOP**
- represents a specific instance of a class
- object in OOP would be like a real, individual car instance that you see on the road, with unique property
values (attributes), for example a specific VRM (car reg.)

**5. Methods**
A "method" is a function that is associated with an object of a particular class. Methods are a way to define the
behaviours of objects.

**6. Properties and Methods**
- A property is some data held by an object. Some people call properties fields or attributes.
- Methods are some code that the object can execute
- Methods can manipulate or use the field data of the object
- Properties are special variables that belong to each individual object instance
- Methods are like functions that are relevant to that class of object

*Static Methods*
- Just as a class can have static properties, like min and max salaries, so it can have static methods
  
*“Static” Class Members*
- properties that are shared among all instances of a class

**7. Advanced OOP Principles in Python**

 Why to use Dataclass Decorators:
- Simplifies the creation of classes with many attributes
- Automatically generates common special methods, reducing boilerplate code
- Improves code readability and maintainability
 
*Polymorphism* allows objects of different classes to be treated as objects of a common base class.

Why use polymorphism:
- Simplifies code by providing a unified interface to multiple classes
- Enhances flexibility, allowing different objects to be used interchangeably
- Supports dynamic method dispatch, allowing the correct method to be called at runtime based on the object's actual type

*Inheritance* allows a class (subclass) to inherit attributes and methods from another class (superclass).

Why use inheritance:
- Avoids code duplication by reusing common attributes and methods
- Organises classes in a hierarchical structure
- Enables polymorphism, allowing objects of different subclasses to be treated uniformly

*Encapsulation* is the principle of bundling data (attributes) and methods (behaviours) that operate on the data within a class.

Why use encapsulation:
- Protects data from unauthorised access and modifications
- Allows validation and control over data access, ensuring data consistency
- Enhances code maintainability by hiding internal implementation details


 ## 3.5 Data Manipulation

 ### Objectives
 
- Explain data manipulation using data engineering tools
- Wrangle and clean more complex datasets using Pandas
- Perform advanced analysis like pivots, aggregates on multiindexed data
- Apply regular expressions to data

**1. Explaining Data Manipulation**
Data manipulation is the method used to modify, structure, format, or sort data so that it becomes useful and more manageable

**2. Unpacking Pandas**

Pandas is an open-source Python library that provides high-performance, easy-to-use data structures and data analysis tools. 
Pandas enables users to:
- Clean
- Transform
- And explore datasets

**3. What is DataFrame?**

A DataFrame is a two-dimensional tabular data structure, similar to a spreadsheet, where data is organised in rows and columns.

**4. Introduction to Series**

- A Series is a one-dimensional labelled array in Pandas
- It can be thought of as a column in a spreadsheet or a simple array
- Series supports various data types and allows for easy indexing and data alignment
- Each element in a Series has a label (an index) that helps in data alignment and retrieval
- Series are used to represent one-dimensional data sets and are an essential component of DataFrames

**5. Loading and Exploring data in Pandas**

- Pandas provides convenient functions to read data from various file formats and explore the structure of the data.
- Pandas provides several functions to read data from various file formats, making it convenient to load and analyse data from different sources, including:
a) Reading Data from CSV Files
b) Reading Data from Excel Files
c) Reading Data from JSON Files
d) Reading Data from SQL Files

**6. Understanding the Structure of Data**

- The head() method is used to display the first few rows of the DataFrame, providing a quick
overview of the data's structure.
- Similarly, the tail() method displays the last few rows of the DataFrame.
- The describe() method generates statistical summaries of the DataFrame. This method provides measures like mean,
median, standard deviation, and quartiles for numerical columns.
- Pandas provides powerful tools to filter data based on specific conditions using Boolean indexing. Boolean indexing allows filtering rows that meet certain criteria. Boolean indexing in pandas is a way to filter data in a DataFrame using True/False values.
- Pandas allows us to arrange data in a particular order using the sort_values() method. Sorting can be done based on one or more
columns in ascending or descending order.
- Pandas supports various data transformation operations, such as adding or removing columns, renaming columns, and converting data types.

**7. Data Wrangling**

Data wrangling is a crucial aspect of data analysis that involves cleaning, transforming, and preparing data to make it suitable for analysis.
Examples of data wrangling include:
- Data cleaning
- Data filtering and sub-setting
- Data transformation

**8. Data Cleaning and Handling Missing Values**

- Pandas makes data cleaning simple with functions like dropna() to remove missing values and fillna() to impute values.
Also useful:
- astype()
- drop_duplicates() - This function identifies duplicate rows based on all column values and keeps only the first
occurrence of each duplicate row
- Filtering data: Pandas provides powerful tools to filter data based on specific conditions.
- Sorting data: Arrange data in a particular order using sort_values() method.
- Pandas allows users to group data based on specific columns using the groupby() method.
- Grouping is useful for segmenting data and performing aggregate operations on each group.
- Once data is grouped, aggregate functions like sum(), mean(), count(), etc., can be applied to each group to compute
meaningful statistics.

**9. Pivot Tables**
- Pandas provides the pivot_table() function, allowing users to create a spreadsheet-style pivot table. This summarises data from a DataFrame, enabling better data analysis and understanding

**10. Merging, Joining, and Concatenating**

The merging, joining and concatenating functions in Pandas allow you to combine or bring together DataFrames in various ways.

**11. Time Series Definition**

Time series data is a sequence of data points ordered by time. The data is indexed by time (for example - days, months, years).

**12 Data/Time Data Types**

- Pandas has datetime data types to represent dates, times, timestamps
- The pd.to_datetime() converts other data types to datetime
- pd.date_range() can generate a DatetimeIndex for a date range

**13. Regular Expressions (Regex)**

- RegEX is a specific search pattern that can be used to easily match, locate and manage text
- To validate an input from the user (e.g. email address)

The syntax of RegEx:

Symbol Meaning
^ Start of input
$ End of input
[A-Za-z0-9] Range of characters
\s Whitespace
\w Word characters
\. . (dot) character
. Any single character
\D A single NON-digit
\S NON-whitespace
\W NON-word characters
+ One or more
{5} Exactly five
{5,} At least five
? One or none
{2,5} Two to five
{,5} Up to five

 ## 3.6 Algorithmic Thinking
 
 ### Objectives
 
- Employ software development tools and techniques for designing, deploying and maintaining secure data products and pipelines, including debugging, version control and testing
- Construct algorithms that correctly and efficiently handle data at scale whilst mitigating risks
- Demonstrate the knowledge of the steps needed to prepare the code for production
 
**1. Intro to Programming**

Programming requires two skills:
1. Algorithmic thinking
2. Knowledge of programming language syntax

To be able to turn your pseudocode into actual code, you need to understand the syntax of your chosen programming language.
Programming relies heavily on abstraction.

Abstraction:

- A general idea or term
- An impractical idea; visionary and unrealistic
- General characteristics apart from concrete realities, specific objects or actual instances
- Absent-mindedness; inattention-
- A work of art

Abstraction in computing:

- Refers to the logical grouping of concepts or objects
- Define/implement the general idea
- Isolate the details
- Helps readability and understanding of our algorithms

Algorithms in computing:

- A set of logical steps to accomplish a task
- One way to solve a problem
- A “recipe of action”
- A way of describing behavior

Algorithms contain:
- Data
- Instructions

Computer science:

- It is a study of algorithms rather than study of computers!
- Often uses pseudo-code to focus on algorithmic thinking
- Not using a computer to compile and run your program forces you to mentally execute your program

**2. Properties of good algorithms**

- Natural language (English)
- Pictures
- Pseudo-code or a specific programming language

**3. The components of algorithms**

1. Data structures – to hold data
2. Instructions – to change data values
3. Conditional expressions – to make decisions
4. Control structures – to act on decisions
5. Modules – to make the algorithm manageable by abstraction; i.e – grouping related components

**4. Elements of a programming language**

- Built-in
- User-defined

**5. Computational performance**

Algorithm Analysis estimates problem cost as a function of growth rate. It is the input that we want to grow, and then observe how
the algorithm “handles” this scaling.

## 3.7 Parallel Programming and Spark

### Objectives

- Identify and explain key concepts of concurrency, parallelism and distributed computing
- Explain key concepts of parallelism and apply within the concept in python programming
- Report on benefits of parallelism
- Analyse perfromance and deployment considerations of parallel programming

 **1. An intorduction to parallelism**
 - parallelism in programming
 - efficiency
 - design considerations
 
 **2. Multiprocessing and Multithreading**
 - multiprocessing - separate CPU memory, perfect for CPU-bond tasks - increase computer speed - achieves parallelism
 - multithreading - sharing CPU and memory - stacking threads - executes multiple threats concurrently - achieves  concurrency

 **3. Concurrency: fork-join model**
 
 **4. Applying processes/ threads to big data**
 
 **5. Distributed Computing**
 
 - uses multiple processors, possibly at different locations
 - enables large scale computations than one machine
 - the model boosts efficcieny and cuts processing time
 - principle vital to modern computing


## 3.8 Spark for Data Engineers

### Objectives

- Evaluate the use of Spark clusters for data processing
- Essential features of data pipelines
- Explain how pipleines are constructed using SparkSQL and Spark streaming
- Evaluate the most common deployment startegies for Spark applications
- Report on benefits of Spark parallelism
- Evaluate platforms similar to Spark

**1. Apache Spark**

- Fast and general purpose cluster computing system for large scale data processing
- High level API's in Jva, Scala, Pythonn and R

Features of Spark:

- reusability
- speed
- advanced analytics
- in memory computing
- real-time stream processing
- lazy evaluation
- dynamic in nature
- fault tolerance

**2. RDD - resilient distributed datasets**

**3. Spark**
  
- runs as application oon existing Spark cluster
- or can run locally
- available in python and scala

## 3.9 Practical skills for data engineers and module consolidation

### Objectives

- Employ software development tools and techniques for designing, deploying and maintaining secure data products and pipelines
- Construct algorithms that correctly and efficiently handle data at scale whilst mitigating risks
- Demonstrate knowledge of the steps needed to prepare the code for production
  
**1. DevOps pipelines**

The benefits:

- Reduced risk
- Shorter review time
- Better code quality
- Faster bug fixes
- Measurable progress
- Faster feedback loops
- Increased collaboration

**2. Continuos Integration**

- Merging all programmers' code frequently
- Automated process
- Checks all code compiles
- Runs tests and quality checks
- Reports on failures

Workflow

- Run tests locally
- Compile the mainline
- Run tests on mainline
- Report on tests

*Best Practise*
- Maintain a code repository
- Automate the build
- Self-testing
- Commit at least daily
- Build every commit
- Every bug has a test
- Builds should be fast
- Life-like test environments
- Easy to get deliverables
- Transparent build results
- Automate deployment

Benefits:
- Integration bugs are found early
- Frequent commits mean easier to
- locate issues
- ‘Current’ build is always testable
- Rigour around testing
- Early access to metrics eg static analysis
- Early feedback on changes

**3. Continuos Delivery**

CD means always having a potentially releasable product.

This means:
• Developing in short cycles
• Ensuring quality of release candidates
• Always having built and tested software

Benefits:
- Faster time to market
- Build the right product
- Improved efficiency and productivity
- Reduced release risk
- Improved quality
- Improved customer satisfaction

**4. Continous Deployment**

- Continuous Deployment is essentially automated continuous delivery
- Continuous delivery relies on a human approval system before a release can take place
- Continuous deployment does not

Benefits:
- Automated release process
- Bugs created recently are easier to fix
- Faster time to market

**5. Containersation**
Packaging software so it is totally self-contained. This means it must contain:
• The actual code
• Libraries
• Runtime environment
• OS kernel

Containers are designed to be:
• OS agnostic
• Write once, run anywhere (or at least more so)
• Lightweight
• Isolated

**5. Infrastructure as Code**

Treating infrastructure in the same way we would code.
• Can be source controlled
• Can be configured at will
• Can be automated

Benefits:
- Cost
- Speed
- Risk

**6. Docker**
It simplifies…
• Environment Setup: Quick and consistent
• Rapid Deployment: Get up and running with a few keystrokes
• Code Distribution: Access code, data, and libraries for analysis
• Collaboration: Work together seamlessly
• Simplicity: Easier than dealing with virtual machines (VMs)

**7. Kubernetes**








