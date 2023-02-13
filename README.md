<h1 class="gap">0x16. C - Simple Shell</h1>

<h3 class="panel-title">Concepts</h3>

 <p><em>For this project, we expect you to look at these concepts:</em></p>
      <ul>
          <li><a href="https://intranet.alxswe.com/concepts/64">Everything you need to know to start coding your own shell</a></li>
          <li><a href="https://intranet.alxswe.com/concepts/350">Approaching a Project</a></li>
      </ul>

<div class="panel-body">
    <h2>Background Context</h2>

<p>Write a simple UNIX command interpreter.</p>

<h2>Resources</h2>

<p><strong>Read or watch</strong>:</p>

<ul>
<li><a href="https://en.wikipedia.org/wiki/Unix_shell" title="Unix shell" target="_blank">Unix shell</a> </li>
<li><a href="https://en.wikipedia.org/wiki/Thompson_shell" title="Thompson shell" target="_blank">Thompson shell</a> </li>
<li><a href="https://en.wikipedia.org/wiki/Ken_Thompson" title="Ken Thompson" target="_blank">Ken Thompson</a> </li>
<li><strong>Everything you need to know to start coding your own shell</strong> concept page</li>
</ul>

<p><strong>man or help</strong>: </p>

<ul>
<li><code>sh</code> (<em>Run <code>sh</code> as well</em>)</li>
</ul>

<h2>Learning Objectives</h2>

<p>At the end of this project, you are expected to be able to <a href="https://fs.blog/feynman-learning-technique/" title="explain to anyone" target="_blank">explain to anyone</a>, <strong>without the help of Google</strong>:</p>

<h3>General</h3>

<ul>
<li>Who designed and implemented the original Unix operating system</li>
<li>Who wrote the first version of the UNIX shell</li>
<li>Who invented the B programming language (the direct predecessor to the C programming language)</li>
<li>Who is Ken Thompson</li>
<li>How does a shell work</li>
<li>What is a pid and a ppid</li>
<li>How to manipulate the environment of the current process</li>
<li>What is the difference between a function and a system call</li>
<li>How to create processes</li>
<li>What are the three prototypes of <code>main</code></li>
<li>How does the shell use the <code>PATH</code> to find the programs</li>
<li>How to execute another program with the <code>execve</code> system call</li>
<li>How to suspend the execution of a process until one of its children terminates</li>
<li>What is <code>EOF</code> / “end-of-file”?</li>
</ul>

<h2>Requirements</h2>

<h3>General</h3>

<ul>
<li>Allowed editors: <code>vi</code>, <code>vim</code>, <code>emacs</code></li>
<li>All your files will be compiled on Ubuntu 20.04 LTS using <code>gcc</code>, using the options <code>-Wall -Werror -Wextra -pedantic -std=gnu89</code></li>
<li>All your files should end with a new line</li>
<li>A <code>README.md</code> file, at the root of the folder of the project is mandatory</li>
<li>Your code should use the <code>Betty</code> style. It will be checked using <a href="https://github.com/holbertonschool/Betty/blob/master/betty-style.pl" title="betty-style.pl" target="_blank">betty-style.pl</a> and <a href="https://github.com/holbertonschool/Betty/blob/master/betty-doc.pl" title="betty-doc.pl" target="_blank">betty-doc.pl</a></li>
<li>Your shell should not have any memory leaks</li>
<li>No more than 5 functions per file</li>
<li>All your header files should be include guarded</li>
<li>Use system calls only when you need to (<a href="https://www.quora.com/Why-are-system-calls-expensive-in-operating-systems" target="_blank">why?</a>)</li>
<li>Write a <code>README</code> with the description of your project</li>
<li>You should have an <code>AUTHORS</code> file at the root of your repository, listing all individuals having contributed content to the repository. Format, see <a href="https://github.com/moby/moby/blob/master/AUTHORS" title="Docker" target="_blank">Docker</a></li>
</ul>

<h3>GitHub</h3>

<p>*<em>There should be one project repository per group. If you and your partner have a repository with the same name in both your accounts, you risk a 0% score. Add your partner as a collaborator. *</em></p>

<h2>More Info</h2>

<h3>Output</h3>

<ul>
<li>Unless specified otherwise, your program <strong>must have the exact same output</strong> as <code>sh</code> (<code>/bin/sh</code>) as well as the exact same error output.</li>
<li>The only difference is when you print an error, the name of the program must be equivalent to your <code>argv[0]</code> (See below)</li>
</ul>

<p>Example of error with <code>sh</code>:</p>

<pre><code>$ echo "qwerty" | /bin/sh
/bin/sh: 1: qwerty: not found
$ echo "qwerty" | /bin/../bin/sh
/bin/../bin/sh: 1: qwerty: not found
$
</code></pre>

<p>Same error with your program <code>hsh</code>:</p>

<pre><code>$ echo "qwerty" | ./hsh
./hsh: 1: qwerty: not found
$ echo "qwerty" | ./././hsh
./././hsh: 1: qwerty: not found
$

</code></pre>

<h3>List of allowed functions and system calls</h3>

<ul>
<li><code>access</code> (man 2 access)</li>
<li><code>chdir</code> (man 2 chdir)</li>
<li><code>close</code> (man 2 close)</li>
<li><code>closedir</code> (man 3 closedir)</li>
<li><code>execve</code> (man 2 execve)</li>
<li><code>exit</code> (man 3 exit)</li>
<li><code>_exit</code> (man 2 _exit)</li>
<li><code>fflush</code> (man 3 fflush)</li>
<li><code>fork</code> (man 2 fork)</li>
<li><code>free</code> (man 3 free)</li>
<li><code>getcwd</code> (man 3 getcwd)</li>
<li><code>getline</code> (man 3 getline)</li>
<li><code>getpid</code> (man 2 getpid)</li>
<li><code>isatty</code> (man 3 isatty)</li>
<li><code>kill</code> (man 2 kill)</li>
<li><code>malloc</code> (man 3 malloc)</li>
<li><code>open</code> (man 2 open)</li>
<li><code>opendir</code> (man 3 opendir)</li>
<li><code>perror</code> (man 3 perror)</li>
<li><code>read</code> (man 2 read)</li>
<li><code>readdir</code> (man 3 readdir)</li>
<li><code>signal</code> (man 2 signal)</li>
<li><code>stat</code> (__xstat) (man 2 stat)</li>
<li><code>lstat</code> (__lxstat) (man 2 lstat)</li>
<li><code>fstat</code> (__fxstat) (man 2 fstat)</li>
<li><code>strtok</code> (man 3 strtok)</li>
<li><code>wait</code> (man 2 wait)</li>
<li><code>waitpid</code> (man 2 waitpid)</li>
<li><code>wait3</code> (man 2 wait3)</li>
<li><code>wait4</code> (man 2 wait4)</li>
<li><code>write</code> (man 2 write)</li>
</ul>

<h3>Compilation</h3>

<p>Your shell will be compiled this way:</p>

<pre><code>gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh
</code></pre>

<h3>Testing</h3>

<p>Your shell should work like this in interactive mode:</p>

<pre><code>$ ./hsh
($) /bin/ls
hsh main.c shell.c
($)
($) exit
$
</code></pre>

<p>But also in non-interactive mode:</p>

<pre><code>$ echo "/bin/ls" | ./hsh
hsh main.c shell.c test_ls_2
$
$ cat test_ls_2
/bin/ls
/bin/ls
$
$ cat test_ls_2 | ./hsh
hsh main.c shell.c test_ls_2
hsh main.c shell.c test_ls_2
$
</code></pre>

<h3>Checks</h3>

<p>The Checker will be released at the end of the project (1-2 days before the deadline). 
We <strong>strongly</strong> encourage the entire class to work together to create a suite of checks covering both regular tests and edge cases for each task. See task <code>8. Test suite</code>.</p>

  </div>

<h2 class="gap">Tasks</h2>

<h3 class="panel-title">
      0. Betty would be proud
    </h3>

<div class="panel-body">
    <p>Write a beautiful code that passes the Betty checks</p>

  </div>

<h3 class="panel-title">
      1. Simple shell 0.1
    </h3>

<div class="panel-body">
    <p>Write a UNIX command line interpreter.</p>

<ul>
<li>Usage: <code>simple_shell</code></li>
</ul>

<p>Your Shell should:</p>

<ul>
<li>Display a prompt and wait for the user to type a command. A command line always ends with a new line.</li>
<li>The prompt is displayed again each time a command has been executed.</li>
<li>The command lines are simple, no semicolons, no pipes, no redirections or any other advanced features.</li>
<li>The command lines are made only of one word. No arguments will be passed to programs.</li>
<li>If an executable cannot be found, print an error message and display the prompt again.</li>
<li>Handle errors.</li>
<li>You have to handle the “end of file” condition (<code>Ctrl+D</code>)</li>
</ul>

<p>You don’t have to:</p>

<ul>
<li>use the <code>PATH</code></li>
<li>implement built-ins</li>
<li>handle special characters : <code>"</code>, <code>'</code>, <code>`</code>, <code>\</code>, <code>*</code>, <code>&amp;</code>, <code>#</code></li>
<li>be able to move the cursor</li>
<li>handle commands with arguments</li>
</ul>

<p><em><code>execve</code> will be the core part of your Shell, don’t forget to pass the environ to it…</em></p>

<pre><code>julien@ubuntu:~/shell$ ./shell
#cisfun$ ls
./shell: No such file or directory
#cisfun$ /bin/ls
barbie_j       env-main.c  exec.c  fork.c  pid.c  ppid.c    prompt   prompt.c  shell.c  stat.c         wait
env-environ.c  exec    fork    mypid   ppid   printenv  promptc  shell     stat test_scripting.sh  wait.c
#cisfun$ /bin/ls -l
./shell: No such file or directory
#cisfun$ ^[[D^[[D^[[D
./shell: No such file or directory
#cisfun$ ^[[C^[[C^[[C^[[C
./shell: No such file or directory
#cisfun$ exit
./shell: No such file or directory
#cisfun$ ^C
julien@ubuntu:~/shell$ echo "/bin/ls" | ./shell
barbie_j       env-main.c  exec.c  fork.c  pid.c  ppid.c    prompt   prompt.c  shell.c  stat.c         wait
env-environ.c  exec    fork    mypid   ppid   printenv  promptc  shell     stat test_scripting.sh  wait.c
#cisfun$ julien@ubuntu:~/shell$
</code></pre>

  </div>

<h3 class="panel-title">
      2. Simple shell 0.2
    </h3>

<div class="panel-body">
    <p>Simple shell 0.1 +</p>

<ul>
<li>Handle command lines with arguments</li>
</ul>

  </div>

<h3 class="panel-title">
      3. Simple shell 0.3
    </h3>

<div class="panel-body">
    <p>Simple shell 0.2 +</p>

<ul>
<li>Handle the <code>PATH</code></li>
<li><code>fork</code> must not be called if the command doesn’t exist</li>
</ul>

<pre><code>julien@ubuntu:~/shell$ ./shell_0.3
:) /bin/ls
barbie_j       env-main.c  exec.c  fork.c  pid.c  ppid.c    prompt   prompt.c  shell_0.3  stat    test_scripting.sh  wait.c
env-environ.c  exec    fork    mypid   ppid   printenv  promptc  shell     shell.c    stat.c  wait
:) ls
barbie_j       env-main.c  exec.c  fork.c  pid.c  ppid.c    prompt   prompt.c  shell_0.3  stat    test_scripting.sh  wait.c
env-environ.c  exec    fork    mypid   ppid   printenv  promptc  shell     shell.c    stat.c  wait
:) ls -l /tmp
total 20
-rw------- 1 julien julien    0 Dec  5 12:09 config-err-aAMZrR
drwx------ 3 root   root   4096 Dec  5 12:09 systemd-private-062a0eca7f2a44349733e78cb4abdff4-colord.service-V7DUzr
drwx------ 3 root   root   4096 Dec  5 12:09 systemd-private-062a0eca7f2a44349733e78cb4abdff4-rtkit-daemon.service-ANGvoV
drwx------ 3 root   root   4096 Dec  5 12:07 systemd-private-062a0eca7f2a44349733e78cb4abdff4-systemd-timesyncd.service-CdXUtH
-rw-rw-r-- 1 julien julien    0 Dec  5 12:09 unity_support_test.0
:) ^C
julien@ubuntu:~/shell$
</code></pre>

  </div>

<h3 class="panel-title">
      4. Simple shell 0.4
    </h3>

<div class="panel-body">
    <p>Simple shell 0.3 +</p>

<ul>
<li>Implement the <code>exit</code> built-in, that exits the shell</li>
<li>Usage: <code>exit</code></li>
<li>You don’t have to handle any argument to the built-in <code>exit</code></li>
</ul>

  </div>

<h3 class="panel-title">
      5. Simple shell 1.0
    </h3>

<div class="panel-body">
    <p>Simple shell 0.4 +</p>

<ul>
<li>Implement the <code>env</code> <strong>built-in</strong>, that prints the current environment</li>
</ul>

<pre><code>julien@ubuntu:~/shell$ ./simple_shell
$ env
USER=julien
LANGUAGE=en_US
SESSION=ubuntu
COMPIZ_CONFIG_PROFILE=ubuntu
SHLVL=1
HOME=/home/julien
C_IS=Fun_:)
DESKTOP_SESSION=ubuntu
LOGNAME=julien
TERM=xterm-256color
PATH=/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
DISPLAY=:0
$ exit
julien@ubuntu:~/shell$
</code></pre>

  </div>

<h3 class="panel-title">
      6. Simple shell 0.1.1
    </h3>

<div class="panel-body">
    <p>Simple shell 0.1 +</p>

<ul>
<li>Write your own <code>getline</code> function</li>
<li>Use a buffer to read many chars at once and call the least possible the <code>read</code> system call</li>
<li>You will need to use <code>static</code> variables</li>
<li>You are not allowed to use <code>getline</code></li>
</ul>

<p>You don’t have to:</p>

<ul>
<li>be able to move the cursor</li>
</ul>

  </div>

<h3 class="panel-title">
      7. Simple shell 0.2.1
    </h3>

<div class="panel-body">
    <p>Simple shell 0.2 +</p>

<ul>
<li>You are not allowed to use <code>strtok</code></li>
</ul>

  </div>

<h3 class="panel-title">
      8. Simple shell 0.4.1
    </h3>

<div class="panel-body">
    <p>Simple shell 0.4 +</p>

<ul>
<li>handle arguments for the built-in <code>exit</code></li>
<li>Usage: <code>exit status</code>, where <code>status</code> is an integer used to exit the shell</li>
</ul>

<pre><code>julien@ubuntu:~/shell$ ./shell_0.4.1
$ exit 98
julien@ubuntu:~/shell$ echo $?
98
julien@ubuntu:~/shell$
</code></pre>

  </div>

<h3 class="panel-title">
      9. setenv, unsetenv
    </h3>

<div class="panel-body">
    <p>Simple shell 1.0 +</p>

<p>Implement the <code>setenv</code> and <code>unsetenv</code> builtin commands</p>

<ul>
<li><code>setenv</code>

<ul>
<li>Initialize a new environment variable, or modify an existing one</li>
<li>Command syntax: <code>setenv VARIABLE VALUE</code></li>
<li>Should print something on stderr on failure</li>
</ul></li>
<li><code>unsetenv</code>

<ul>
<li>Remove an environment variable</li>
<li>Command syntax: <code>unsetenv VARIABLE</code></li>
<li>Should print something on stderr on failure</li>
</ul></li>
</ul>

  </div>

<h3 class="panel-title">
      10. cd
    </h3>

<div class="panel-body">
    <p>Simple shell 1.0 +</p>

<p>Implement the builtin command <code>cd</code>:</p>

<ul>
<li>Changes the current directory of the process.</li>
<li>Command syntax: <code>cd [DIRECTORY]</code></li>
<li>If no argument is given to <code>cd</code> the command must be interpreted like <code>cd $HOME</code></li>
<li>You have to handle the command <code>cd -</code></li>
<li>You have to update the environment variable <code>PWD</code> when you change directory</li>
</ul>

<p><code>man chdir</code>, <code>man getcwd</code></p>

  </div>

<h3 class="panel-title">
      11. ;
    </h3>

<div class="panel-body">
    <p>Simple shell 1.0 +</p>

<ul>
<li>Handle the commands separator <code>;</code></li>
</ul>

<pre><code>alex@~$ ls /var ; ls /var
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
alex@~$ ls /hbtn ; ls /var
ls: cannot access /hbtn: No such file or directory
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
alex@~$ ls /var ; ls /hbtn
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
ls: cannot access /hbtn: No such file or directory
alex@~$ ls /var ; ls /hbtn ; ls /var ; ls /var
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
ls: cannot access /hbtn: No such file or directory
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
alex@~$
</code></pre>

  </div>

<h3 class="panel-title">
      12. &amp;&amp; and ||
    </h3>

<div class="panel-body">
    <p>Simple shell 1.0 +</p>

<ul>
<li>Handle the <code>&amp;&amp;</code> and <code>||</code> shell logical operators</li>
</ul>

<pre><code>alex@~$ ls /var &amp;&amp; ls /var
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
alex@~$ ls /hbtn &amp;&amp; ls /var
ls: cannot access /hbtn: No such file or directory
alex@~$ ls /var &amp;&amp; ls /var &amp;&amp; ls /var &amp;&amp; ls /hbtn
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
ls: cannot access /hbtn: No such file or directory
alex@~$ ls /var &amp;&amp; ls /var &amp;&amp; ls /var &amp;&amp; ls /hbtn &amp;&amp; ls /hbtn
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
ls: cannot access /hbtn: No such file or directory
alex@~$
alex@~$ ls /var || ls /var
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
alex@~$ ls /hbtn || ls /var
ls: cannot access /hbtn: No such file or directory
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
alex@~$ ls /hbtn || ls /hbtn || ls /hbtn || ls /var
ls: cannot access /hbtn: No such file or directory
ls: cannot access /hbtn: No such file or directory
ls: cannot access /hbtn: No such file or directory
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
alex@~$ ls /hbtn || ls /hbtn || ls /hbtn || ls /var || ls /var
ls: cannot access /hbtn: No such file or directory
ls: cannot access /hbtn: No such file or directory
ls: cannot access /hbtn: No such file or directory
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp
alex@~$
</code></pre>

  </div>

<h3 class="panel-title">
      13. alias
    </h3>
<div class="panel-body">
    <p>Simple shell 1.0 +</p>

<ul>
<li>Implement the <code>alias</code> builtin command</li>
<li>Usage: <code>alias [name[='value'] ...]</code>

<ul>
<li><code>alias</code>: Prints a list of all aliases, one per line, in the form <code>name='value'</code></li>
<li><code>alias name [name2 ...]</code>: Prints the aliases <code>name</code>, <code>name2</code>, etc 1 per line, in the form <code>name='value'</code></li>
<li><code>alias name='value' [...]</code>: Defines an alias for each <code>name</code> whose <code>value</code> is given. If <code>name</code> is already an alias, replaces its value with <code>value</code></li>
</ul></li>
</ul>

  </div>

<h3 class="panel-title">
      14. Variables
    </h3>

<div class="panel-body">
    <p>Simple shell 1.0 +</p>

<ul>
<li>Handle variables replacement</li>
<li>Handle the <code>$?</code> variable</li>
<li>Handle the <code>$$</code> variable</li>
</ul>

<pre><code>julien@ubuntu:~/shell$ ./hsh
$ ls /var
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  snap  spool  tmp
$ echo $?
0
$ echo $$
5104
$ echo $PATH
/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
$ exit
julien@ubuntu:~/shell$
</code></pre>

  </div>

<h3 class="panel-title">
      15. Comments
    </h3>

<div class="panel-body">
    <p>Simple shell 1.0 +</p>

<ul>
<li>Handle comments (<code>#</code>)</li>
</ul>

<pre><code>julien@ubuntu:~/shell$ sh
$ echo $$ # ls -la
5114
$ exit
julien@ubuntu:~/shell$
</code></pre>

  </div>

<h3 class="panel-title">
      16. File as input
    </h3>

<div class="panel-body">
    <p>Simple shell 1.0 +</p>

<ul>
<li>Usage: <code>simple_shell [filename]</code></li>
<li>Your shell can take a file as a command line argument</li>
<li>The file contains all the commands that your shell should run before exiting</li>
<li>The file should contain one command per line</li>
<li>In this mode, the shell should not print a prompt and should not read from <code>stdin</code></li>
</ul>

  </div>

