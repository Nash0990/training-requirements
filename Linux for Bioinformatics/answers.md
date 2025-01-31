# Answers to questions from "Linux for Bioinformatics"

Q1:  What is your home directory? 

A: 
```/home/ubuntu```

Q2: What is the output of this command? (ls)

A: 
```hello_world.txt```

Q3: What is the output of each ls command ?

A:
```
my_folder:

my_folder2:
hello_world.txt
```

Q4: What is the output of each?

A:
```
my_folder:

my_folder2:

my_folder3:
hello_world.txt
```

Q5: Why didn't that work ?

A: The key pair created by AWS initially is configured to give permission to log in as user 'ubuntu' only. Since we are not logging in as 'ubuntu' user the key pair does not work.

Q6: What was the solution?

A: Either we can use the password uthenticated way to log in as 'sudouser' (which would not be very secure way) or we could generate a ssh key pair between the host and the remote server with 'sudouser' as 
the user. Generate public/private key pair using the ```ssh-keygen``` command, and then copy the public SSh key to the remote server with ```ssh-copy-id``` command or by manually creating the '.ssh' folder
and add the public key string to the 'authorized_keys' file.

Q7: what does the sudo docker run part of the command do? and what does the salmon swim part of the command do?

A: ```sudo docker run``` part of the command calls the docker application as sudo, and the ```run``` part tells the application to run the container mentioned. The ```salmon swim``` command actually calls
the salmon application from within the docker container and passes the command ```swim``` to it. As per the docs swim command "perform super-secret operation", in all seriousness it probabaly checks if the 
salmon tool is working fine and also checks for the version.

Q8: What is the output of this command?

A:
```serveruser is not in the sudoers file.  This incident will be reported.```

Q9: what does ```-c bioconda``` do?

A: This parameter asks conda to search for the tool in the bioconda channel. Conda channels are locations where packages are stored and maintained.

Q10: What does the ```-o athal.ga.gz``` part of the command do?

A: This parameter directs the curl command output from stdout to the mentioned file.

Q11: What is a ```.gz``` file?

A: A file with ```.gz``` extension means that the file has been compressed using Gunzip application.

Q12: What does the ```zcat``` command do?

A: ```zcat``` is a command line tool used to view(cat) compressed/zipped files, without havinf to uncompress it compleately.

Q13: what does the head command do? 

A: As the name says, it prints the top lines(10 lines by default) of any file. 

Q14: what does the number 100 signify in the command? 

A: Its the argument passed onto the -n parameter that tells head command to print top 100 lines of the file.

Q15: What is ```|``` doing?

A: The ```|``` is a pipe tool, it helps in redirecting output of a command into an input of the command that comes after the pipe.

Q16: What format are the downloaded sequencing reads in?

A: The file downloaded is in SRA format.

Q17: What is the total size of the disk?

A: 7.7 GB

Q18. How much space is remaining on the disk?

A: 3.5 GB

Q19: What went wrong?

A: Ran out of storage space on the instance.

Q20: What was your solution?

A: Added the ```--gzip``` parameter to the fastq-dump command inorder to get the output fastq file gzipped.
