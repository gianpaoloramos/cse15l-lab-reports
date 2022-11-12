# Week 5 Lab Report: Researching Commands

## find

find is a command that is used to find files and directories and perform subsequent operations on them. 

*  **-name 'file name'**
  
This option searches for files specified by the 'file name'. This is helpful for finding specific files within a directory.

```
MacBook-Air-3:docsearch gianramos$ find technical -name biomed
technical/biomed
```

```
MacBook-Air-3:docsearch gianramos$ find technical -name 911report
technical/911report
```

This is what happens when you search for a file that doesn't exist: 

```
MacBook-Air-3:docsearch gianramos$ find technical -name cse15l
MacBook-Air-3:docsearch gianramos$ 
```

*  **-empty**
  
This option searches for empty files and directories. This could be useful when searching for empty files and directories, either to delete them or add things to them.

(I created an empty folder for this example.)
```
MacBook-Air-3:docsearch gianramos$ find technical -empty
technical/empty
```

This is what happens when you there are no empty files:

```
MacBook-Air-3:docsearch gianramos$ find technical -empty
MacBook-Air-3:docsearch gianramos$ 
```

When there are multiple empty files/folders:

```
MacBook-Air-3:docsearch gianramos$ find technical -empty
technical/empty
technical/empty2
```

* **-user 'name'**

This option searches for files owned by user 'name'. This is useful if you are working on a shared computer or server, so you are able to identify who owns which files.

biomed shows up since I am the owner of this file.
```
MacBook-Air-3:docsearch gianramos$ find technical -name biomed -user gianramos
technical/biomed
```

This is what happens when I try to search for a user that doesn't exist.
```
MacBook-Air-3:docsearch gianramos$ find technical -name biomed -user csestudent
find: -user: csestudent: no such user
```
Using it on the remote server:

```
[cs15lfa22ph@ieng6-203]:~:128$ find perl5 -user cs15lfa22ph
perl5
```

