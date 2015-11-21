##Terminal Pro - Tutsplus Course Notes
###Unix Philosophy
___
write programss that 
+ do one thing well
+ work together
+ handle text streams (universal interface)
##Advanced Bash Commands for Directory Navigation
___
+ pushd ~/mydir (pushes mydir in dirs)
+ popd (pops top directory from dirs and moves into it)
##Meta Commands
___
+ man command (opens man page for help
+ which vim (shows dir)
+ file
+ basename (give me just the base name of a path)
+ clear (clear the terminal, just scrolls up)
+ ctrl-k (clear)
##Archiving (zipping from commandline)
+ gzip file.txt (zipping a file)
+ gzip -d file.gz to file.txt (unzip file)
+ zip myZip.zip file1.txt file2.txt
+ unzip myZip.zip (replace none)
+ tar -cvzf archive.tar.gz file1.txt file2.txt
+ tar -xvzf archive.tar.gz
##Inputs to Outputs
___
Filedescriptor: an abstract way to point to an input or output
[Filedescriptor on Wikipedia](https://en.wikipedia.org/wiki/File_descriptor)
Standard File Descriptors are:
nbr | sys name | Display name
---|---|
#0|stdin|Standard Input
#1|stdout|Standard Output
#2|stderr|Standard Error
##Changing the Standard Output
___
ls -l > listings.txt (writes all subdirs/files of dir)
ls -l >> listings.txt (appends to listings.txt)
ls -l | grep 'Nov 20' > filesNov20.txt
##Changing to Standard Error
___
ls NoDir 2> dirs.txt (change output to stderr: 2>

2> change output to stderr
&> combine stdout and stderr
##Redirecting with cat command
___
stdin to stdout
cat > from-stdinput.txt
this is the first line.
tihs is the second line.


Bye!
(hit ctrl-c will finish cat command and redirecting input  to from-input.txt)




