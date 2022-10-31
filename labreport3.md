# Week 5 Lab Report
## The command-line and alternate ways I choose
I choose to find the command-line options and alternate ways for 'find' command
The website I've visited and cited is `https://www.digitalocean.com/community/tutorials/how-to-use-find-and-locate-to-search-for-files-on-linux`
## Find *
### Introduction
`
find *
`

This method will return every single file that under current direcotory. The essential difference between this command and the'ls' command is that the ls command will tell us the file that The files or folders contained in the current path, but find * will help us drill down all the way through all subfolders until we find each individual file and return all those files. Additionally, the The format of the output is also slightly different from 'ls', and the example below will show the difference. 

### Example 1
In this example. I directly input `find *` into the workinf direcotry(in this case, skill-demo 1), the command helps us to return every single files contains in  all of the sub files inside of this directory. 

```
biomed/1471-2105-3-17.txt
biomed/1471-230X-3-3.txt
biomed/ar430.txt
biomed/1471-2156-3-4.txt
biomed/1471-2466-2-4.txt
biomed/1471-2296-3-18.txt
biomed/1471-2105-3-16.txt
more files here...
biomed/1471-2121-2-3.txt
biomed/1471-213X-1-11.txt
biomed/1472-684X-1-5.txt
biomed/1476-4598-1-6.txt
government
government/About_LSC
government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
government/Media/Politician_Practices.txt
more files here...
government/Media/defend_yourself.txt
government/Media/Towson_Attorney.txt
government/Media/NJ_Legal_Services.txt
government/Media/Bridging_legal_aid_gap.txt
government/Media/Legal_Aid_campaign.txt
government/Media/Aid_Gets_7_Million.txt
plos
plos/pmed.0020273.txt
plos/journal.pbio.0030032.txt
plos/pmed.0020065.txt
plos/pmed.0020071.txt
plos/pmed.0020059.txt
plos/pmed.0010039.txt
more files here 
plos/pmed.0020040.txt
plos/pmed.0020068.txt
plos/journal.pbio.0020012.txt
plos/pmed.0020281.txt
plos/pmed.0020242.txt
```

This is just prt of the result that is been returned, there are much more lines in 'more files here" under the same directory. From the result, we can oberve that `find *` not only return evey single file under the current folder. and subfolder, it also tell us the subfile names such as  `plos`, `government`, before showing us what is files inside of folder,  which van give us a clearer picture of what is the "file structure' under current folder. 

### Example 2
 
In this example I gave a basic compasison between `ls` and `find*` in order to give a clearer picture of the difference between these two command. 

```
(base) kevinmbp@Kevins-MacBook-Pro-2 technical % ls
911report       biomed          government      plos
```

```
base) kevinmbp@Kevins-MacBook-Pro-2 technical % find *
biomed/1471-2105-3-17.txt
biomed/1471-230X-3-3.txt
biomed/ar430.txt
biomed/1471-2156-3-4.txt
biomed/1471-2466-2-4.txt
biomed/1471-2296-3-18.txt
biomed/1471-2105-3-16.txt
more files here...
biomed/1471-2121-2-3.txt
biomed/1471-213X-1-11.txt
biomed/1472-684X-1-5.txt
biomed/1476-4598-1-6.txt
government
government/About_LSC
government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
government/Media/Politician_Practices.txt
more files here...
government/Media/defend_yourself.txt
government/Media/Towson_Attorney.txt
government/Media/NJ_Legal_Services.txt
government/Media/Bridging_legal_aid_gap.txt
government/Media/Legal_Aid_campaign.txt
government/Media/Aid_Gets_7_Million.txt
plos
plos/pmed.0020273.txt
plos/journal.pbio.0030032.txt
plos/pmed.0020065.txt
plos/pmed.0020071.txt
plos/pmed.0020059.txt
plos/pmed.0010039.txt
more files here 
plos/pmed.0020040.txt
plos/pmed.0020068.txt
plos/journal.pbio.0020012.txt
plos/pmed.0020281.txt
plos/pmed.0020242.txt
```

From this comparison, we can calearly see that the `ls` command only give us us a name of folder under current directory, but the `find *` command, same as before, told us every singel file names under corrent directory, we can also see that the names the two command returned are in the different format, and I will present this difference more clearly in the next example. 

### Example 3
In this example I will present the differences in the format of the content returned by the two commands even they return the same content. 

```
(base) kevinmbp@Kevins-MacBook-Pro-2 911report % ls
chapter-1.txt           chapter-13.3.txt        chapter-6.txt
chapter-10.txt          chapter-13.4.txt        chapter-7.txt
chapter-11.txt          chapter-13.5.txt        chapter-8.txt
chapter-12.txt          chapter-2.txt           chapter-9.txt
chapter-13.1.txt        chapter-3.txt           preface.txt
chapter-13.2.txt        chapter-5.txt

(base) kevinmbp@Kevins-MacBook-Pro-2 911report % find *
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

In this exampel, I use command `cd` to get into the 911 report folder, this is the inner most folder in 'technical' which means it only contains the `txt` files. Theoretically, `ls` and `find *` will return the same content for us. But we can see that if we use `ls` command, we will get a horizontal list about the files in the '911report', but command `find *` gave us a list that is vertial, in another words, there is only one file names evey single line. This is the also a diffrence between these two command despite the diffrence in the previous two exmaples. 


## Find Size
### Introduction
`find * +-size` is a command that help us to find some specific files that fullfill the size requirement, and since this is a command that will help us to find the files that has some specifc property, we need to manually decided what is the requirement, in this case, size. There some special character that represent different meanings, `-` represnet smaller. `+` represent larger, `k` represent kilobyte and `m` represnet `megabyte`, which are the unit of the size of the files, we will use and expalin those characters in the examples. 

### Example 1
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

### Example 2
In this exmaple, we will show how to use `+` in the command

```
(base) kevinmbp@Kevins-MacBook-Pro-2 911report % find * -size +200k
chapter-13.4.txt
chapter-13.5.txt
chapter-3.txt
```

From this exmaple we can see that we put in the exactly same command but we change`-` into`+` before we put in the required size, so this command change into that "find all of the files that is larger than the 200k in the folder 911report". From here, we can see that there are only 3 files that is larger than 200k. 

### Example 3
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


## Find Type
### Introduction
In the previous command, we have talked about how to find some files that is within specific range of size, in this part we will see how to find some specific files by searching by their own types. In the following examples we will see how to search different types of files. 

### Example 1
In this example, wew ill indoruce one type of `-type` command which helps us to find all of the directorys under current folder. 

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

### Example 2

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

### Example 3
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

