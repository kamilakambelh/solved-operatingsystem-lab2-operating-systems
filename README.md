Download Link: https://assignmentchef.com/product/solved-operatingsystem-lab2-operating-systems
<br>
Goal: The lab helps student to

<ul>

 <li>Review basic shell commands and practice with <em>vim </em>on Linux, Mac OS X.</li>

 <li>Review C programming with compiling and running a program on Linux, Mac OS X.</li>

</ul>

Content:

<ul>

 <li>Practice with <em>vim </em>– text editor.</li>

 <li>Programming with C language.</li>

 <li>Compile a program with Makefile.</li>

</ul>

Result:

<ul>

 <li>After doing the lab, student can type a program without GUI on Linux/Mac OS C by <em>vim</em>.</li>

 <li>Student can compile and run a program using Makefile.</li>

</ul>

<h1>1      Introduction</h1>

1.1 Vim

Vim is the editor of choice for many developers and power users. It‘s a “modal” text editor based on the vi editor written by Bill Joy in the 1970s for a version of UNIX. It inherits the key bindings of vi, but also adds a great deal of functionality and extensibility that are missing from the original vi. Vim has two modes for users:

<ul>

 <li>Command mode: allows user to do functions such as find, undo, etc.</li>

 <li>Insert mode: allows user to edit the content of text.</li>

</ul>

To turn the <em>Insert </em>mode to <em>Command </em>mode, we type <em>ESC </em>key or <em>Crtl</em>−<em>C</em>. Otherwise, to enter the <em>Insert </em>mode, type i or I, a, A, o, O. Some of basic commands in <em>V im</em>:

<ul>

 <li>Save: enter :w</li>

 <li>Quit without Save and discard the change: enter :q!</li>

 <li>Save and Quit: enter :wq</li>

 <li>Move the cursor to the top of file: gg</li>

 <li>Move to the bottom: G</li>

 <li>Find a letter/string by going forward: enter /[letter/string] &lt;Enter&gt;</li>

 <li>Find a letter/string by going backward: enter ?[letter/string] &lt;Enter&gt;</li>

 <li>Repeat the previous finding: enter n</li>

 <li>Repeat the previous finding by going backward: enter N</li>

 <li>Delete a line: enter dd</li>

 <li>Undo: enter u</li>

 <li>Redo: enter Ctrl-R</li>

</ul>

Furthermore, <em>V im </em>has a mode called “visual” that allows user to chose a paragraph for copying or, moving. To enter this mode, we need to turn the editor into <em>Command </em>mode and press “v”. After that, user use “arrow” keys to chose the paragraph, and then use the following commands:

<ul>

 <li>Copy: enter y</li>

 <li>Cut: enter d</li>

 <li>Paste: enter p</li>

</ul>

1.2 C programming on Linux/Mac OS X

GNU C Coding Standards

<ul>

 <li>Keep the length of source lines to 79 characters or less, for maximum readability in the widest range of environments.</li>

 <li>Put a comment on each function saying what the function does, what sorts of arguments it gets, and what the possible values of arguments mean and are used for.</li>

 <li>Please explicitly declare the types of all objects. For example, you should explicitly declare all arguments to functions, and you should declare functions to return int rather than omitting the int.</li>

</ul>

Reference: <a href="https://www.gnu.org/prep/standards/standards.html">http://www.gnu.org/prep/standards/standards.html</a><a href="https://www.gnu.org/prep/standards/standards.html">.</a> Formatting your source code

Compiling process: It is important to understand that while some computer languages (e.g. Scheme or Basic) are normally used with an interactive interpreter (where you type in commands that are immediately executed). C source codes are always compiled into binary code by a program called a “compiler” and then executed. This is actually a multi-step process which we describe in some detail here.

source

code                                                                                                      executable

(.c, .cc, .h)                                                                                             binaries

Preprocessor  Compiler  Assembler  Linker

Figure 1.1: C Compiling scheme

Steps in compiling process:

<ul>

 <li>Preprocessor</li>

 <li>Compiler</li>

 <li>Assembler</li>

 <li>Linker</li>

</ul>

Compilers and Libraries: Apple provides a customized/optimized GNU CC, with backends for C, C++, Objective-C and Objective-C++. Compilers for many other languages are available either precompiled (such as the XL Fortran Advanced Compiler from IBM), or can be compiled from source, which is not any harder in general than compiling the same source on, say, Linux or FreeBSD. The LLVM compiler is the next-generation compiler, introduced in Mac OS X. In Xcode of Mac OS X, the LLVM compiler uses the Clang front end to parse source code and turn it into an interim format.

Figure 1.2: Clang in Mac OS X

Figure below shows a C program compiled in step by step.

<table width="564">

 <tbody>

  <tr>

   <td width="564">% Preprocessed source f i l e$ gcc −E [−o hello . cpp ]                         hello . c% Assembly code$ gcc −S [−o hello .S]                          hello . c% Binary           f i l e$ gcc −c [−o hello . o ]                        hello . c% Executable             f i l e$ gcc [−o hello ]                     hello . c</td>

  </tr>

 </tbody>

</table>

1

2

3

4

5

6

7

8

9

10

11

<h1>2      Practice</h1>

2.1 Compile and run a program

Steps for creating a program

In general, the compiling progress includes these steps:

<ol>

 <li>Create source code file hello.c</li>

</ol>

<table width="528">

 <tbody>

  <tr>

   <td width="528">#include &lt;stdlib .h&gt;#include &lt;stdio .h&gt;int main( int argc , char ∗∗ argv ) { printf (“Hello , ␣World!
” );return 0;}</td>

  </tr>

 </tbody>

</table>

1

2

3

4

5

6

7

<ol start="2">

 <li>Create object file:</li>

</ol>

$ gcc −c souce_code_file . c <em># Example :</em>

$ gcc −c             hello . c

<em># or</em>

$ gcc −c −o hello . o hello . c

<ol start="3">

 <li>Create executable file:</li>

</ol>

<table width="528">

 <tbody>

  <tr>

   <td width="224">$ gcc −o executable_file <em># Example :</em>$ gcc −o hello                    hello . o</td>

   <td width="176">object1 . o object2 . o</td>

   <td width="127">. . .</td>

  </tr>

 </tbody>

</table>

We can compile the program directly from the source code file without the step of creating object file. However, this way can cause the difficulty when identifying errors.

<ol start="4">

 <li>Create executable file:</li>

</ol>

<table width="528">

 <tbody>

  <tr>

   <td width="224">$ gcc −o executable_file <em># Example :</em>$ gcc −o hello                    hello . c</td>

   <td width="124">src1 . c src2 . c</td>

   <td width="180">. . .</td>

  </tr>

 </tbody>

</table>

<ol start="5">

 <li>Run the program:</li>

</ol>

<table width="528">

 <tbody>

  <tr>

   <td colspan="2" width="207">$ ./ executable_file<em># Example :            to     l i s t       the</em>$ ls</td>

   <td colspan="2" width="61"><em>crated</em></td>

   <td width="96"><em>executable</em></td>

   <td width="62"><em>binary</em></td>

   <td width="102"><em>f i l e</em></td>

  </tr>

  <tr>

   <td width="154">hello                        hello . c</td>

   <td colspan="2" width="62"> </td>

   <td colspan="4" width="312">hello . o</td>

  </tr>

  <tr>

   <td width="154"><em># To execute                 the</em>$ ./ hello</td>

   <td colspan="2" width="62"><em>binary</em></td>

   <td colspan="4" width="312"><em>f i l e</em></td>

  </tr>

  <tr>

   <td width="154"></td>

   <td width="52"></td>

   <td width="9"></td>

   <td width="52"></td>

   <td width="96"></td>

   <td width="62"></td>

   <td width="102"></td>

  </tr>

 </tbody>

</table>

<ul>

 <li>During compiling a program, the source code can make some errors. The compiler provides debuggers that show the information of errors. The structure of showing errors: &lt;file&gt;:&lt;row&gt;:&lt;column_letter&gt;:&lt;type&gt;:&lt;detail&gt;</li>

 <li>For example, error 1:</li>

</ul>

<table width="528">

 <tbody>

  <tr>

   <td width="383">$ gcc −o hello . o −c hello . c hello . c :1:18: fatal error : stdo .h: No such compilation terminated .</td>

   <td width="44">f i l e</td>

   <td width="101">. . .</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>From the example of error 1:

  <ul>

   <li>Error file: hello.c</li>

   <li>Error line: 1</li>

   <li>The column of error letter: 18</li>

   <li>Type of error: error</li>

   <li>Detail info: stdo.h not found</li>

  </ul></li>

</ul>

2.2 Makefile

A makefile is a file containing a set of directives used with the make build automation tool. Most often, the makefile directs make on how to compile and link a program. Using C/C++ as an example, when a C/C++ source file is changed, it must be recompiled. If a header file has changed, each C/C++ source file that includes the header file must be recompiled to be safe. Each compilation produces an object file corresponding to the source file. Finally, if any source file has been recompiled, all the object files, whether newly made or saved from previous compilations, must be linked together to produce the new executable program.[1] These instructions with their dependencies are specified in a makefile. If none of the files that are prerequisites have been changed since the last time the program was compiled, no actions take place. For large software projects, using Makefiles can substantially reduce build times if only a few source files have changed. A makefile consists of “rules” in the following form:

<table width="564">

 <tbody>

  <tr>

   <td width="564"><em># comment</em><em># ( note :               the &lt;tab&gt; in             the command line</em><em># is            necessary        for      make to      work)</em>target :                  dependency1 dependency2          . . .&lt;tab&gt; command</td>

  </tr>

 </tbody>

</table>

Where,

<ul>

 <li>target: a target is usually the name of a file that is generated by a program; examples of targets are executable or object files. A target can also be the name of an action to carry out, such as “clean”.</li>

 <li>dependency1, dependency2,…: a dependency (also called prerequisite) is a file that is used as input to create the target. A target often depends on several files. However, the rule that specifies a recipe for the target need not have any prerequisites. For example, the rule containing the delete command associated with the target “clean” does not have prerequisites.</li>

 <li>command: Needed commands is used for performing rules.</li>

</ul>

For example, we have three source code files including main.c, hello.h, hello.c.

<table width="564">

 <tbody>

  <tr>

   <td width="564"><em>//         File :      main . c</em>#include ” hello .h”int main() {helloworld ();return 0;}</td>

  </tr>

 </tbody>

</table>

<em>// File : hello . h </em>void helloworld (void );

<em>//        File :         hello . c</em>

#include ” hello .h”

#include &lt;stdio .h&gt;

void helloworld (void) { printf (“Hello , ␣world
” );

}

In this example, we compile .c files into object files .o, and then link all of object files into a single binary. Firstly, that is the process of compiling source code files into object files.

<ul>

 <li>o: main function in main.c calls helloworld() which is declared in hello.h. Thereby, to compile main.c, we need the information declared from hello.h. To create main.o, we need hello.h and main.c. Therefore, the rule for creating main.o is:</li>

</ul>

main . o : main . c hello .h

gcc −c main . c

<ul>

 <li>o: similar to the rule of main.o, we need two files named hello.c and hello.h to create hello.o. Note that hello.c using printf() in the library stdio.h to print the output on screen. However, this is the library integrated with GCC, so we do not need to fill in the dependency of the rule.</li>

</ul>

hello . o : hello . c hello .h gcc −c hello . o

<ul>

 <li>hello: Because helloworld is declared in hello.h, but it is defined in hello.c and compiled into the binary in hello.o, therefore, if the main function calls this function, we need to link hello.o with main.o to create the final binary. This file depends on hello.o and main.o.</li>

</ul>

all : main . o hello . o gcc main . o hell . o −o hello

<ul>

 <li>Finally, we can add the rule of clean to remove all of object files and binaries in case of compiling an entire program.</li>

</ul>

<table width="528">

 <tbody>

  <tr>

   <td width="128">clean : rm −f</td>

   <td width="399">∗.o hello</td>

  </tr>

 </tbody>

</table>

The final result of Makefile:

<table width="564">

 <tbody>

  <tr>

   <td width="564">all : main . o hello . o gcc main . o hello . o −o hellomain . o : main . c            hello .hgcc −c main . chello . o : hello . c hello .h gcc −c hello . cclean :rm −f ∗.o hello</td>

  </tr>

 </tbody>

</table>

With this Makefile, to re-compile the whole program, we call “make all”. To remove all of object files and binaries, we call “make clean”. If we need to create an object file main.o, we call “make main.o”. If we only call “make”, the default rule of Makefile is executed – “make all”.

References

<ul>

 <li>Coding style by GNU: <a href="https://www.gnu.org/prep/standards/standards.html">http://www.gnu.org/prep/standards/standards.html</a><a href="https://www.gnu.org/prep/standards/standards.html">.</a></li>

 <li>C programming

  <ul>

   <li>Brian Kernighan, and Dennis Ritchie, <em>“The C Programming Language”</em>, Second Edition</li>

   <li>Randal E. Bryant and David R. O’Hallaron, <em>“Computer systems: A Programmer‘s Perspective”</em>, Second Edition</li>

  </ul></li>

 <li>More information about Vim: <a href="http://vim.wikia.com/wiki/Vim_Tips_Wiki">http://vim.wikia.com/wiki/Vim_Tips_Wiki</a></li>

 <li>Makefile:

  <ul>

   <li>A simple Makefile tutorial <a href="http://www.cs.colby.edu/maxwell/courses/tutorials/maketutor/">http://www.cs.colby.edu/maxwell/courses/ </a><a href="http://www.cs.colby.edu/maxwell/courses/tutorials/maketutor/">tutorials/maketutor/</a></li>

   <li>GNU Make Manual <a href="https://www.gnu.org/software/make/manual/make.html">https://www.gnu.org/software/make/manual/make.</a></li>

  </ul></li>

</ul>

<a href="https://www.gnu.org/software/make/manual/make.html">html</a>

<h1>3      Exercises</h1>

3.1 Questions

<ol>

 <li>Compiling a program in the first time usually takes a longer time in comparisonwith the next re-compiling. What is the reason?</li>

 <li>Can we use Makefile for other programming languages?</li>

 <li>In case of source code files located in different places, how can we write a Makefile?</li>

</ol>

3.2 Programming exercises

Two header files named findsubstr.h and readline.h have the following contents:

<table width="564">

 <tbody>

  <tr>

   <td width="328"><em>//           findsubstr . h</em>#ifndef FIND_SUBSTR_H#define FIND_SUBSTR_H int find_sub_string (const char ∗str ,#endif</td>

   <td width="236">const char ∗sub );</td>

  </tr>

 </tbody>

</table>

<em>//         readline . h</em>

#ifndef READ_LINE_H

#define READ_LINE_H int read_line (char ∗ str );

#endif

<ol>

 <li>Writing findsubstr.c implementing find_sub_string() function: find_sub_string gets two strings including str and sub. If str contains the substring – substr that is similar to sub, the program returns the first letter of substr in str. Otherwise, the program returns -1. For example, find_sub_string(“abcbc”, “bc”) returns 1, while find_sub_string(“abcbc”, “xy”) returns -1.</li>

 <li>Writing readline.c implementing read_line(): read_line() function gets data from stdin (keyboard), line-by-line. The content from stdin will be recorded on the parameter of this function named str. The result of read_line() is the number of read letters, or -1 if it reads EOF (end of file). For example, with the input string below:</li>

</ol>

Hello ,         world

Operating system

Computer Science and Engineering

After calling the function, read_line() writes “Hello,world” into str and returns 12. The second calling will write “Operating system” into str and return 16. The third calling will write “Computer Science and Engineering” into str and return -1.

<ol start="3">

 <li>Writing main.c to create an executable file named mygrep that has function similar to grep command on Linux/Mac OS X shell. In detail, mygrep gets the input being a string, and then reads one line of strdin at a time (each line does not exceed 100 letters). After that, the program checks which line contains the string being entered by user, and prints these lines on screen. Student finish main.c file, then write a Makefile to compile the program at least two targets:

  <ul>

   <li>all: create mygrep from other files.</li>

   <li>clean: remove all of object files, binaries.</li>

  </ul></li>

</ol>

<table width="564">

 <tbody>

  <tr>

   <td width="302"><em>// main . c</em>#include &lt;stdio .h&gt;#include ” readline .h”#include ” findsubstr .h”int main( int argc , char ∗ argv [ ] )<em>// Implement mygrep</em>}#endif</td>

   <td width="262">{</td>

  </tr>

 </tbody>

</table>

Note: As these exercises are graded automatically, thereby, student need to implement the program by the requirements mentioned above. Student compress all of files (.c, .h, Makefile) in a folder named Student ID by .zip format.

Makefile example

<table width="564">

 <tbody>

  <tr>

   <td width="564">FC=gfortranCC=gccCP=cp.PHONY:         all       cleanOBJS = mylib . o mylib_c . o<em># Compiler              flags</em>FFLAGS = −g −traceback −heap−arrays 10 −I . −L/usr/ lib64 −lGL −lGLU −lX11 −lXextCFLAGS = −g −traceback −heap−arrays 10 −I . −lGL −lGLU −lX11 −lXextMAKEFLAGS = −W −wPRJ_BINS=helloPRJ_OBJS = $( addsuffix . o , $(PRJ_BINS)) objects := $(PRJ_OBJS) $(OBJS) all : myapp%.o : %.f90$(FC) −D_MACHTYPE_LINUX $&lt; −c −o <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="90b4d0">[email protected]</a>%.o : %.F$(FC) −D_MACHTYPE_LINUX $&lt; −c −o <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="1c385c">[email protected]</a>%.o : %.c$(CC) −D_MACHTYPE_LINUX               $&lt; −c −o <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="486c08">[email protected]</a>myapp:         objects$(CC) $(CFLAGS) $^ $( objects ) −o <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="5a7e1a">[email protected]</a>clean :@echo “Cleaning␣up . . ” rm −f ∗.o rm −f $(PRJ_BINS)</td>

  </tr>

 </tbody>

</table>

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

23

24

25

26

27

28

29

30

31

32

33

34

35

36

37

38

39

40

<h1>Revision History</h1>

<table width="537">

 <tbody>

  <tr>

   <td width="79">Revision</td>

   <td width="68">Date</td>

   <td width="114">Author(s)</td>

   <td width="276">Description</td>

  </tr>

  <tr>

   <td width="79">1.0</td>

   <td width="68">11.03.15</td>

   <td width="114">PD Nguyen</td>

   <td width="276">created</td>

  </tr>

  <tr>

   <td width="79">1.1</td>

   <td width="68">11.09.15</td>

   <td width="114">PD Nguyen</td>

   <td width="276">add introduction and exercise section</td>

  </tr>

  <tr>

   <td width="79">2.0</td>

   <td width="68">25.02.16</td>

   <td width="114">PD Nguyen</td>

   <td width="276">Restructure the content to form an tutorial</td>

  </tr>

  <tr>

   <td width="79">2.1</td>

   <td width="68">20.08.16</td>

   <td width="114">DH Nguyen</td>

   <td width="276">Update C and Vim to Appendix</td>

  </tr>

 </tbody>

</table>


