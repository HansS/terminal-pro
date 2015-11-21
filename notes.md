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
Copy from [Bash Programming Introduction](http://www-rohan.sdsu.edu/doc/bash/HOWTO/Bash-Prog-Intro-HOWTO.html#toc1)
___
<H2><A NAME="s3">3. All about redirection</A>        </H2>

<H2><A NAME="ss3.1">3.1 Theory and quick reference</A>
        </H2>

<P> There are 3 file descriptors, stdin, stdout and stderr (std=standard).
<P>
<P>Basically you can:
<OL>
<LI> redirect stdout to a file</LI>
<LI> redirect stderr to a file</LI>
<LI> redirect stdout to a stderr </LI>
<LI> redirect stderr to a stdout </LI>
<LI> redirect stderr and stdout to a file </LI>
<LI> redirect stderr and stdout to stdout </LI>
<LI> redirect stderr and stdout to stderr</LI>
</OL>

1 'represents' stdout and 2 stderr.
<P> A little note for seeing this things: with the less command you can view both stdout 
(which will remain on the buffer) and the stderr that will be printed on the screen, but erased as 
you try to 'browse' the buffer. 
<H2><A NAME="ss3.2">3.2 Sample: stdout 2 file  </A>
</H2>

<P> This will cause the ouput of a program to be written to a file.
<BLOCKQUOTE><CODE>
<PRE>
        ls -l > ls-l.txt
        
</PRE>
</CODE></BLOCKQUOTE>

Here, a file called 'ls-l.txt' will be created and it will contain what you would see on the 
screen if you type the command 'ls -l' and execute it.
<H2><A NAME="ss3.3">3.3 Sample: stderr 2 file  </A>
</H2>

<P> This will cause the stderr ouput of a program to be written to a file.
<BLOCKQUOTE><CODE>
<PRE>
        grep da * 2> grep-errors.txt
        
</PRE>
</CODE></BLOCKQUOTE>

Here, a file called 'grep-errors.txt' will be created and it will contain what you would see
the stderr portion of the output of the 'grep da *' command.
<H2><A NAME="ss3.4">3.4 Sample: stdout 2 stderr</A>
        </H2>

<P> This will cause the stderr ouput of a program to be written to the same filedescriptor 
than stdout.
<BLOCKQUOTE><CODE>
<PRE>
        grep da * 1>&amp;2 
        
</PRE>
</CODE></BLOCKQUOTE>

Here, the stdout portion of the command is sent to stderr, you may notice that in differen ways.
<H2><A NAME="ss3.5">3.5 Sample: stderr 2 stdout        </A>
</H2>

<P> This will cause the stderr ouput of a program to be written to the same filedescriptor 
than stdout.
<BLOCKQUOTE><CODE>
<PRE>
        grep * 2>&amp;1
        
</PRE>
</CODE></BLOCKQUOTE>

Here, the stderr portion of the command is sent to stdout, if you pipe to less, you'll see that
lines that normally 'dissapear' (as they are written to stderr) are being kept now (because
they're on stdout). 
<H2><A NAME="ss3.6">3.6 Sample: stderr and stdout 2 file       </A>
</H2>

<P> This will place every output of a program to a file. This is suitable sometimes 
for cron entries, if you want a command to pass in absolute silence.  
<BLOCKQUOTE><CODE>
<PRE>
        rm -f $(find / -name core) &amp;> /dev/null 
        
</PRE>
</CODE></BLOCKQUOTE>
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




