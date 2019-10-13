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
**Difference**



# Pipe
While redirect is used to pass output to either a file or stream, pipe is used to pass output to another program or utility.
```console
ls -alh | less
```
Basically, it connect the standard output of the first utility to the second utility.
