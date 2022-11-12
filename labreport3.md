# Week 5 Lab Report
## The command-line and alternate ways I choose
I choose to find the command-line options and alternate ways for 'find' command
The website I've visited and cited is `https://www.digitalocean.com/community/tutorials/how-to-use-find-and-locate-to-search-for-files-on-linux`



## 1)Find Size
### Introduction
`find * +-size` is a command that help us to find some specific files that fullfill the size requirement, and since this is a command that will help us to find the files that has some specifc property, we need to manually decided what is the requirement, in this case, size. There some special character that represent different meanings, `-` represnet smaller. `+` represent larger, `k` represent kilobyte and `m` represnet `megabyte`, which are the unit of the size of the files, we will use and expalin those characters in the examples. 

### Example 1.1
In this example, we will show how to use `-` in the command. 

```
(base) kevinmbp@Kevins-MacBook-Pro-2 911report % find * -size -200k
chapter-1.txt
chapter-10.txt
chapter-11.txt
chapter-12.txt
chapter-13.1.txt
chapter-13.2.txt
chapter-13.3.txt
chapter-2.txt
chapter-5.txt
chapter-6.txt
chapter-7.txt
chapter-8.txt
chapter-9.txt
preface.txt
```

In this example, the command we put in is `find * -size -200k`. We can see that the condition is adding after `find x`, which is the syntax of this command. `-` here represent 'lower than', so the whole command means that 'find all of the files that is smaller than 200k in the folder 911report. 

### Example 1.2
In this exmaple, we will show how to use `+` in the command

```
(base) kevinmbp@Kevins-MacBook-Pro-2 911report % find * -size +200k
chapter-13.4.txt
chapter-13.5.txt
chapter-3.txt
```

From this exmaple we can see that we put in the exactly same command but we change`-` into`+` before we put in the required size, so this command change into that "find all of the files that is larger than the 200k in the folder 911report". From here, we can see that there are only 3 files that is larger than 200k. 

### Example 1.3
In this example we will put `+` and `-` together to make a more complex command. 

```
(base) kevinmbp@Kevins-MacBook-Pro-2 911report % find * -size +100k -size -200k
chapter-1.txt
chapter-12.txt
chapter-13.2.txt
chapter-13.3.txt
chapter-6.txt
chapter-7.txt
chapter-9.txt
```

From this example we can see that we can actually put two command togerther to make a new commnad, in this case, since the command we put in is ` find * -size +100k -size -200k `, it represent that we are looking for te file that is smaller than 200k but larger than 100k in the filder 911 report. Remember, we nee to tyoe in `-size` twice to tell the terminal that 100k and 200k are all represent to the size of the files. 


## 2)Find Type
### Introduction
In the previous command, we have talked about how to find some files that is within specific range of size, in this part we will see how to find some specific files by searching by their own types. In the following examples we will see how to search different types of files. 

### Example 2.1
In this example, we will indoruce one type of `-type` command which helps us to find all of the directorys under current folder. 

```
(base) kevinmbp@Kevins-MacBook-Pro-2 technical % find * -type d
911report
biomed
government
government/About_LSC
government/Env_Prot_Agen
government/Alcohol_Problems
government/Gen_Account_Office
government/Post_Rate_Comm
government/Media
plos
```

In this example, the command we put in is '`find * -type d`, and d here stand for 'directory', from the result, we can see that we have got what we expected. There are five folder undet 'technical' for the folder 'government', there are sixth sub folders inside of it. 

### Example 2.2

In this example, we will see how to find all of the files by `-type` command, and the difference between just type in `find * ` is that we no longer need the subfolders but only single files. 

```
(base) kevinmbp@Kevins-MacBook-Pro-2 technical % find * -type f 
biomed/1472-6882-2-10.txt
biomed/1471-2350-3-1.txt
more files here... 
biomed/1476-4598-1-6.txt
government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
government/About_LSC/Progress_report.txt
government/About_LSC/Strategic_report.txt
government/About_LSC/Comments_on_semiannual.txt
government/About_LSC/Special_report_to_congress.txt
more files here...
government/Media/Legal_Aid_campaign.txt
government/Media/Aid_Gets_7_Million.txt
plos/pmed.0020273.txt
plos/journal.pbio.0030032.txt
plos/pmed.0020065.txt
plos/pmed.0020071.txt
more files here...
plos/journal.pbio.0020440.txt
plos/pmed.0010062.txt
plos/pmed.0020242.txt
```

From this example, the command we type in is `-type f`, and f stand for regular file, so we can see that enven though we still get a lot of files, they do not include subfiles such as "Media", "About_LSC" under the 'government' folder, this is the main difference between just simply type in `find *` in this situation. 

### Example 2.3
In this example, we will show that we can also adding some ore restrictions after the type. 

```
(base) kevinmbp@Kevins-MacBook-Pro-2 technical % find * -type f -name "pmed.*.txt"
plos/pmed.0020273.txt
plos/pmed.0020065.txt
more files here...
plos/pmed.0020120.txt
plos/pmed.0020040.txt
plos/pmed.0020068.txt
plos/pmed.0020281.txt
plos/pmed.0020242.txt
```

In this example, the command we put in is `(base) kevinmbp@Kevins-MacBook-Pro-2 technical % find * -type f -name "pmed.*.txt`, this means that find all of the files that contains "pmed' before the ending and is a 'txt' file, and we can see that all of the files that return contains what we need, there are 'pmed' before numbers and all of the, are txt files. 

## 3)Find by time
### Introduction
`find -time num ` is a find method that can help us find the files that last had their meta information changed more or less than a specific number of days. Similar with the size method we introduced before, we can use `-` or `+` to let our device now the number we type in is the upper or the lower limit of the number of days. We will show how to use them in the following examples. 

### Example 3.1
In this example we will use `find * -ctime +20 ` to find the files we want. 
```
(base) kevinmbp@Kevins-MacBook-Pro-2 911report % find *  -ctime +20
chapter-1.txt
chapter-10.txt
chapter-11.txt
chapter-12.txt
chapter-13.1.txt
chapter-13.2.txt
chapter-13.3.txt
chapter-13.4.txt
chapter-13.5.txt
chapter-2.txt
chapter-3.txt
chapter-5.txt
chapter-6.txt
chapter-7.txt
chapter-8.txt
chapter-9.txt
preface.txt
```
From this examples, the command we type in is `find * -ctime +20`, `find *` will help us to find all of the file under '911 report', but the restriction we gave is `-ctime +2-`, which means 'finding all of the file whose last modified date is greater than 20 days', we can see that all of the files under this directory has been modfied more than 20 days before. 

### Example 3.2
In this examples we will use `-` to filter files. 
```
(base) kevinmbp@Kevins-MacBook-Pro-2 911report % find * -ctime -20             
(base) kevinmbp@Kevins-MacBook-Pro-2 911report % 
```
The only difference between this command and the command we use in the last examples is that we cahnge `+ ` into ` - ` in this example, so the meaning of this command become "finding all of the file whose last modified date is less than 20 days", from the previous examples we have known that the all of the files under this directory has been modified greater than 20 days, in another words, we would not find anything in the command we just put in, and we got what we expected. 

### Examples 3.3
In this example, we will show how to set the upper and lower bond at the same time. 
```
(base) kevinmbp@Kevins-MacBook-Pro-2 911report % find * -ctime -100 -ctime +20
chapter-1.txt
chapter-10.txt
chapter-11.txt
chapter-12.txt
chapter-13.1.txt
chapter-13.2.txt
chapter-13.3.txt
chapter-13.4.txt
chapter-13.5.txt
chapter-2.txt
chapter-3.txt
chapter-5.txt
chapter-6.txt
chapter-7.txt
chapter-8.txt
chapter-9.txt
preface.txt
```
In this examples, the command we put in is `find * -ctime -100 -ctime +20`, which means "finding all of the file whose last modified date is less than 100 days but more than 20 days". And we can see that all of the files were modified within 100 days but more than 20 days. 