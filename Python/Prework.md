# Prework Notes

## SQL & Relational Databases

**Summary, from SQLBOLT.COM**
- SQL is a relational type of database that utilizes tables -- her job is tables.
- SELECT statements = queries
- Creating conditions for your requests makes it easier for the database to quickly return information because you are loading less of it.
- Tables that share information about a single entity need to have a primary key that identifies that entity uniquely across the database. Auto-incrementing integer, string, etc.
- Each database has its own supported set of mathematical, string, and date functions that can be used in a query, which you can find in their own respective docs.
- *SELECT col_expression AS expr_description, … FROM mytable;*
- The GROUP BY clause works by grouping rows that have the same value in the column specified.
- Apply WHERE so that the correct number of rows are updated, unless you want all rows to be changed.
- Use SELECT to make sure you are querying the correct data before deleting them, if you want to double check.
- Create schemas with the types of data. 

**Screenshots**
<img width="409" alt="Lesson 1" src="https://github.com/maddieamie/reading-notes/assets/118625447/d920dd58-ea9d-44da-8db5-322587639097">
<img width="605" alt="Lesson 2" src="https://github.com/maddieamie/reading-notes/assets/118625447/fbafe357-acc0-4d44-882a-5b95a4f8652c">
<img width="559" alt="Lesson 3" src="https://github.com/maddieamie/reading-notes/assets/118625447/b0b6180b-5a66-4c65-af4f-60db4c9fee6e">
<img width="608" alt="Lesson 4" src="https://github.com/maddieamie/reading-notes/assets/118625447/3a43e1b8-7b4b-4b11-b8ed-c8689c5c05ed">
<img width="594" alt="Lesson 5" src="https://github.com/maddieamie/reading-notes/assets/118625447/3b3f52b6-0b79-4496-825d-3f0d8ecbe7a5">
<img width="585" alt="Lesson 6" src="https://github.com/maddieamie/reading-notes/assets/118625447/49971161-a2eb-4a3a-982c-c1b102013e60">
<img width="590" alt="Lesson 7" src="https://github.com/maddieamie/reading-notes/assets/118625447/653c97d8-807f-4473-9e63-a0002bf54031">
<img width="571" alt="Lesson 8" src="https://github.com/maddieamie/reading-notes/assets/118625447/e8ca50b6-807a-43ef-9e46-9644f7322c8e">
<img width="540" alt="Lesson 9" src="https://github.com/maddieamie/reading-notes/assets/118625447/2c9a3b35-e3ce-47e4-bcc4-9500792b9ec1">
<img width="605" alt="Lesson 10" src="https://github.com/maddieamie/reading-notes/assets/118625447/f0e2cf51-2360-4458-aba9-f6c2b62561e6">
<img width="586" alt="Lesson 11" src="https://github.com/maddieamie/reading-notes/assets/118625447/79a426cb-19f5-4912-9dd3-9f831bdc55c3">
<img width="705" alt="Lesson 12" src="https://github.com/maddieamie/reading-notes/assets/118625447/d8eea154-24da-4f95-8d35-aa25dbe89759">
<img width="693" alt="Lesson 13" src="https://github.com/maddieamie/reading-notes/assets/118625447/617e807e-16c0-4b8c-8720-9e33fa4b0572">
<img width="698" alt="Lesson 14" src="https://github.com/maddieamie/reading-notes/assets/118625447/1a12ce7e-69d6-4db5-896d-d148582adf7f">
<img width="697" alt="Lesson 15" src="https://github.com/maddieamie/reading-notes/assets/118625447/f0a60b77-b06a-44f6-ada7-b072fe74f6d5">
<img width="652" alt="Lesson 16" src="https://github.com/maddieamie/reading-notes/assets/118625447/bd125a8c-1630-48d7-b079-c6281b3c09a5">
<img width="705" alt="Lesson 17" src="https://github.com/maddieamie/reading-notes/assets/118625447/52f07408-a008-44c8-ab8a-6abd925eb46f">
<img width="685" alt="Lesson 18" src="https://github.com/maddieamie/reading-notes/assets/118625447/90c22dd4-ce65-4db3-9f99-edd092c2af0d">


**Notes**
<img width="579" alt="Useful operators for SQL" src="https://github.com/maddieamie/reading-notes/assets/118625447/af19ab73-512d-4faa-8b5a-5d0f6f006b8f">
<img width="609" alt="Common aggregate functions" src="https://github.com/maddieamie/reading-notes/assets/118625447/3ede1c9e-6876-4617-9161-0f7721959dac">

## Command Line

**The Command Line** 
- bash -- which stands for Bourne again shell
- echo - shows your current shell
- arrow up to previous commands

**Basic Navigation** 
- pwd- print working directory
- ls - shows what's in our current directory
- ls -l long listing about the files in directory
- ls /etc list the directory's contents
- root / - top of the directory
- absolute path -> begin with / in relation to root directory
- relative path -> specify a location in relation to where we currently are in the system, does not begin with /
- ~ a shortcut for your home directory
- . reference to your current directory
- ../../ go up two directories, .. up a directory
- cd / == cd ~/Documents == cd ../../
- cd sends you back to your home directory without any arguments

  **More About Files**
  - Linux is case sensitive
  - handle files with spaces --> cd 'Holiday Photos'
  - ls -a list the contents of a directory, including hidden files.
  
  **Manual Pages**
  - man <command> - Look up the manual page for a particular command.
- man -k <search term> -Do a keyword search for all manual pages containing the given search term.
- /<term> -Within a manual page, perform a search for 'term'
- n -After performing a search within a manual page, select the next found item.

 **File Manipulation**
- mkdir + name -- make directory
- rmdir [options] <Directory> - remove directory
-  -p which tells mkdir to make parent directories as needed (demonstration of what that actually means below). The second one is -v which makes mkdir tell us what it is doing 
- touch -- make blank files
- cp [options] <source> <destination> -- copy
- mv [options] <source> <destination> -- move
- rm [options] <file> -- cannot be undone, but removes or deletes files
- -r When rm is run with the -r option it allows us to remove directories and all files and directories contained within. -i with -r will make it interactive so you know which files you are removing with prompts first. 
