# linux_task1

# Adjust_Task: The assigned task involves reading data in text format from 'file.txt,' counting the number of lines in the file, and determining the occurrences of the character 'Z.' Additionally, the to identify the line numbers associated with the terms 'Junior,' 'Platform,' and 'Engineer,' and then replace the word 'Junior' with 'Senior' in the file.


My approach to the task is to first create a Git repository named 'task-1.' Next, I'll clone the repository to my local machine.I will create a text file and input the data.


Step 1: Create a Git repository

here i login to github UI , go to repositories and create new repo.
(We can create and initate repo from command prompt as well)

Step 2: Clone the repository to local
	Command: git clone ".git"
	Go to the folder using CD command 

Step 3: Create 'file.txt' using vi editor.
        Command: vi file.txt
        
        
Step 4: Add and save random string data into this file.
        press i to insert data and :wq! to save and close
### Add the file.txt to repo with below commands
        git add file.txt 
        git commit -m "Adding file.txt"
        git push
        
### Simillarly adding the data to README.md and push the file to repo with commit message   
        
Below are the questions asked with solution :

1. How many lines in this file?

   Command: cat file.txt | wc -l 

### cat command is used to view the content in the file
### wc -l counts the number of lines

   output : 98 (with page numbers removed)

2. How many “Z” Characters in this file ?

   Command: grep -o 'Z' file.txt | wc -l
   
### grep command used for searching text
### -o Show only the matched parts of the line.
### | pipe. It takes the output of the command on its left (grep -o 'Z' file.txt) and feeds it as input to the command on its right (wc -l).

   Output: 44
   

3. Find on which line is “Junior”, “Platform” and “Engineer”,not case sensitive.

   Command: grep -ino '\(Junior\|Platform\|Engineer\)' file.txt 
   OR 
   Command: grep -ino -e 'Junior' -e 'Platform' -e 'Engineer' file.txt
   
### -i Ignore case in the pattern
### n - Display line numbers.
###-o Show only the matched parts of the line.
### escaped parentheses \( and \) group the alternatives, and \| serves as a logical OR. it can be like either or
### -e is used to specify multiple patterns to search in a single command

     Output: 28:PlatForm
             65:Junior
             88:EngineeR
             

### this is the same as above to get the whole line 
3. grep -in -e 'Junior' -e 'Platform' -e 'Engineer' file.txt

   Output: 28:COJILxEOhBRPlatFormjc00OhTT6ve
           65:x7t2vMJunior0qcMHQtnVGhlggfnry
           88:7B6nmS3lLJaEngineeR28pzseTejdm
           

5. Change “Junior” to “Senior”

### sed expression : s/old-pattern/new-pattern/flags

   Command: sed -i 's/Junior/Senior/gI' file.txt 
   
### sed command: is used to make chabnges in the text file
### s/ -- This indicates that it's a substitution command.
### -i -- modify the contents of the file directly, rather than producing output to the terminal.
### s/Junior/SeniorgI -- Finds every occurrence of the word 'Junior' and replace it with 'Senior'
### / -- This separates the old pattern from the new pattern.




