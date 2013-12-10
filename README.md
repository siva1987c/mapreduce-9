MapReduce on EC2
================
created by Vineet Jain, September 2013

This project is was created to implement MapReduce on gigabytes worth of text documents and calculate the co-occurrence
rate between the words in the text file and a specified target word. To optimize parallelization, this project was run
on Amazon EC2 servers as well.

Parameters can be specified in the configuration file, titled conf.xml

###Usage:
Convert your input .txt file into a .seq file that is readable by hadoop
`make generate-input myinput=YOUR_INPUT_FILE.txt`

You can launch a hadoop job by running the following command:
`$ hadoop jar proj1.jar Proj1 -conf conf.xml <params> <input> <intermediateDir> <outDir>`

<params> set `-Dcombiner=true` to turn combiner on or `-Dcombiner=false` to turn it off  
         set `-DrunJob2=true` to run the second job or `-DrunJob2=false` to only run the first job  
<input> the location of your .seq file 
<intermediateDir> your intermediate directory (holds the output of the first Mapreduce Job) which is used as input for the second job  
<outDir> your outDir (holds the output of the second Mapreduce job)  
