# MapReduce versus Hadoop MapReduce
## MapReduce
The MapReduce programming technique was designed to analyze massive data sets across a cluster. In this Jupyter notebook, you'll get a sense for how Hadoop MapReduce works; however, this notebook will run locally rather than on a cluster.

The biggest difference between Hadoop and Spark is that Spark tries to do as many calculations as possible in memory, which avoids moving data back and forth across a cluster. Hadoop writes intermediate calculations out to disk, which can be less efficient. Hadoop is an older technology than Spark and one of the cornerstone big data technologies.

If you click on the Jupyter notebook logo at the top of the workspace, you'll be taken to the workspace directory. There you will see a file called "songplays.txt". This is a text file where each line represents a song that was played in the Sparkify app. The MapReduce code will count how many times each song was played. In other words, the code counts how many times the song title appears in the list.

## MapReduce versus Hadoop MapReduce:
Don't get confused by the terminology! MapReduce is a programming technique. Hadoop MapReduce is a specific implementation of the programming technique.

Some of the syntax will look a bit funny, so be sure to read the explanation and comments for each section. You'll learn more about the syntax in later lessons.

Run each of the code cells below to see the output.

## Solution:
- Install mrjob library. This package is for running MapReduce jobs with Python
- Create two functions to count how many times each song was played:
1. The map function, the code reads in the txt file one line at a time. The map steps outputs a set of tuples that look like this:<br/>
(Deep Dreams, 1)<br/>
(Data House Rock, 1)<br/>
(Deep Dreams, 1)<br/>
(Data House Rock, 1)<br/>
(Broken Networks, 1)<br/>
(Data House Rock, 1)<br/>
etc.....<br/>
2. The reduce funtion thatcombines all of the values by keys and sums the values:<br>
(Deep Dreams, [1, 1, 1, 1, 1, 1, ... ])<br>
(Data House Rock, [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, ...])<br>
(Broken Networks, [1, 1, 1, ...]<br>
With the output<br>
(Deep Dreams, 1131)<br>
(Data House Rock, 510)<br>
(Broken Networks, 828)<br>