Linux command line is really powerful by do operation with few stroke. This time I will list some linux command line operations that is
extremely useful for beginner to linux. The command line, terminal, and cmd are thought as synonymy in this blog. Command and operation 
are thought synonymy too.

# find help within linux command line
## man
You can always run `man` to get manual of specific operation, most operation comes with a manual.
for example

```console
man rm
```
You can even use `man` to get the manual of `man` operation

```console
man man
```
# which
`which` will give you the of the directory of the requested operation.
The following line give you the directory of calender application in linux

```console
which cal
```
# locate
If you have no idea where is the file, you can use `locate` command, it will give you all the location of files contain
the pattern you give
```console
locate cal
```

# updatedb 
Either `locate` and `which` will use the database to query result. Basically, Linux will update every day. If you just make changes to you files or directories, you
can use 
```console
sudo updatedb
```


# roam directories
## where are you and who you are
Before we start the journey, we need to know something first. 
When you open linux terminal. You probably will see information like this

```console
user_information@computer_information: ~$
```
The `~` indicate you are now in Sthe home directory.
You can use

```console # this gives you your current working directory
pwd
```

You will see
```console
/home/chunhui
```

it should return a directory like this `home\user_name`

The `$` indicate that you are a regular user to this system. By regular, I mean you don't have high level operation authority to 
some operation. You can use `sudo` command, but we will talk that later. When you get the authority of `root`, which is the administrator
operation authority, you will see a `#` instead of `$`

## start roaming
Are you ready, tight the safety belt and rev up you engine.
### ls command
Now we are on the `home\user` directory, we can use `ls` command to ls what are inside current path
```console
ls
```
Almost all commands have operations. You don't need to worry about this now. You can use command with options to get more powerful.
```console
ls -a # this will show all everything including hidden files or directories
ls -l # this will give you a long version of the return 
ls -a -l # you can use multiple options at one time
ls -al # it could even be simpler
```

### cd command
`cd` command is a very import command. Before using `cd` command, I need to teach you some basic knowledge about linux directory. 
Like Windows and Mac OS, Linux is made up of directories or folds. `\` stands for the root directory, and there are many directories 
inside and directories and files inside those directories, and so on.
Paths start with `\` are considered as absolute path, otherwise relative paths.
```console
cd \home\user #use absolute path
cd Documents #use relative path
```
You can also use `cd` command to bring you back to home. There are three ways to do that
```console
cd ~
cd
cd /home/user
```

In the `ls` section, I've tell you how to explore what are inside a directory.

```console
bowtie-0.12.8  Desktop  Documents  Downloads  examples.desktop  Junk  Music  Pictures  Public  R  snap  Templates  Videos
```

### pushd and popd
You can always use `cd` to bring you back to the home and take you deep inside any directory. However, it is still
very important to get back to previous directory after you finish operation in another directory. You can let `pushd` to
lead you to some directory and then use `popd` back.
```console
pushd /home/user/Documents
popd #it will bring you back
```


# file and directory operation
You can use `mv` command to mv a file or a diretory to another directory or use it to rename
```console
mkdir test # create a test directory undercurrent path
mv test ~ # move the test directory to home path
touch test.txt # create a empty txt file
mv test.txt text_rename.txt # rename the file
```
Basically, `touch` will create a file if it doesn't exist, while change the time stamp otherwise. It will be treated as 
a new file after the time stamp has been changed. Either `touch` and `mkdir` can take as many parameters as you want, 
they're just gonna to create many files and directory.







