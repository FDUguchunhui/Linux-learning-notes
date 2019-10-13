# Redirection

If you use `echo`
```console
echo "hello world"
```
By default, it will print "hello world" on you screen (shell), which means it use screen as standard output.

You can use your output as input for another application. There are three kinds of redirection.
## 1. stand output
```console
echo "this should be in a file" > somefile.txt # if not exist, will be created.
# If the file already exists, by default, echo will replace the content.
echo "this is the text should be in the file for real" > somefile.txt 
echo "this is the second line" >> somefile.txt  # >> will append output behind
cat somefile.txt # you can use cat to check. What cat does is concatenate two files and print on screen
```
You can redirect `ls` output to a file.
```console
ls -alh > listouput # -alh means all, long, and human readable size
cat listoutput
```

## 2. stand error output
```console
ls -alh somefilethatdoesntexit >> listoutput
# ls: cannot access 'somefilethatdoesntexit': No such file or directory
ls -alh somefilethatdoesntexit 2> err.txt
cat err.txt
```

**To sum up**, redirection redirect the output into a file.


# Pipe
While redirect is used to pass output to either a file or stream, pipe is used to pass output to another program or utility.
```console
ls -alh | less
```
The next examples show how to use `|` with filtering
```console
echo -e 'dave:we\nuser:love\nsomeone:linux\nsomeone:linux' > file.txt #  enable interpretation of backslash escapes
#example 1 
cat file.txt | cut -d: -f2 # '-d:' means use ':' as delim, '-f2' select only the second field
# you will get this result
# we
# love
# linux

# example 2
cat file.txt | sort -bf # -b ignoring leading blanks -f ignoring case

# example 3
cat file.txt | uniq # only print unique lines

# example 4
cat file.txt | grep user

```


Basically, it connect the standard output of the first utility to the second utility.

# &&
Run the second command if only the first command succeed
```console
echo -e 'dave:we\nuser:love\nsomeone:linux' > file.txt #  enable interpretation of backslash escapes

#example 1
ls file.txt && echo 'astonishing success'

#example 2


```
# some other useful commands
`grep` is a very useful regular expression matching command, it will print lines that match a pattern in files
```console
grep someone file.txt

# Let create another demo file
echo -e 'someone said something\nthis is unrelated' > err.txt
grep someone ./* # grep lines that contain 'someone' on all files on current path

# you should get something like this
# grep: ./Courses: Is a directory
#./err.txt:someone said something
#./file.txt:someone:linux


# pipe complex
```
grep someone ./* | uniq | cut -d: -f1
```




