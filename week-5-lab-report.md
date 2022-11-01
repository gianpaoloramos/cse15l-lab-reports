# Week 5 Lab Report: Researching Commands

## less

less is a command that displays the contents of a file or a command output one page at a time.

* **-E**
  
This option makes it so that less automatically exits when it reaches the end of the file, so you don't have to press q. I guess this could be a minor quality of life option that just removes the inconvenience and small time to press q at the end if you just want to browse through the files quickly. (I'm not really sure how to display this behavior through a code block).

* **-p 'pattern'**

This option makes it so that less starts at the first occurrence of 'pattern' in the file. This is useful for quickly finding certain files.

```
less -p "biomed" find-results.txt
technical//biomed
technical//biomed/1472-6807-2-2.txt
technical//biomed/1471-2350-4-3.txt
technical//biomed/1471-2156-2-3.txt
technical//biomed/1471-2156-3-11.txt
technical//biomed/1471-2121-3-10.txt
technical//biomed/1471-2172-3-4.txt
technical//biomed/gb-2002-4-1-r2.txt
technical//biomed/gb-2003-4-6-r41.txt
technical//biomed/1471-2466-1-1.txt
technical//biomed/1471-2199-2-10.txt
technical//biomed/1471-2202-2-9.txt
technical//biomed/cc991.txt
...
```

* **-N** 
  
This option makes it so that line numbers are shown next to all the files. This is useful for quickly seeing how many files are in a folder/directory.

```
less -N find-results.txt
      1 technical/
      2 technical//find-results.txt
      3 technical//government
      4 technical//government/About_LSC
      5 technical//government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
      6 technical//government/About_LSC/Progress_report.txt
      7 technical//government/About_LSC/Strategic_report.txt
      8 technical//government/About_LSC/Comments_on_semiannual.txt
      9 technical//government/About_LSC/Special_report_to_congress.txt
     10 technical//government/About_LSC/CONFIG_STANDARDS.txt
     11 technical//government/About_LSC/commission_report.txt
     12 technical//government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
     13 technical//government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
     14 technical//government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
```

## find

find is a command that is used to find files and directories and perform subsequent operations on them. 

*  **-name 'file name'**
  
This option searches for files specified by the 'file name'. This is helpful for finding specific files within a directory.

```
MacBook-Air-3:docsearch gianramos$ find technical -name biomed
technical/biomed
```

*  **-empty**
  
This option searches for empty files and directories. This could be useful when searching for empty files and directories, either to delete them or add things to them.

(I created an empty folder for this example.)
```
MacBook-Air-3:docsearch gianramos$ find technical -empty
technical/empty
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

## grep

grep is a command that is used to search for regular expressions. It takes a string and a file, and prints out all lines in that file that match the string. 

* **-c**

This option makes it so that it prints only a count of the lines that match a pattern. This is useful if you are just looking for the count of the files/directories that contain the pattern.

```
MacBook-Air-3:docsearch gianramos$ grep -c "chapter" find-texts.txt
16
```

* **-w** 

This option makes it so that it searches only for files/directories that match the whole word. This is useful if the pattern you are looking for is a common substring of other files, so that you can filter those out. 

(Without -w, this search would print out all the files containing "chapter" as well. Because there is no file with just the word "chap", there is no result.)
```
MacBook-Air-3:docsearch gianramos$ grep -w "chap" find-texts.txt
MacBook-Air-3:docsearch gianramos$
```

* **-v**

This option makes it so that it prints all the lines that don't match the pattern. This is useful if you want to look for directories or folders among a large list of files.

```
MacBook-Air-3:docsearch gianramos$ grep -v ".txt" find-texts.txt
technical
technical/government
technical/government/About_LSC
technical/government/Env_Prot_Agen
technical/government/Alcohol_Problems
technical/government/Gen_Account_Office
technical/government/Post_Rate_Comm
technical/government/Media
technical/plos
technical/biomed
technical/911report
```

