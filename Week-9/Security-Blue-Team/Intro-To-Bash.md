# Introduction to Bash PT2 - Week 9 [(Security Blue Team)](https://elearning.securityblue.team/home/courses/free-courses/introduction-to-bash#content)

## Introduction to AWK, GAWK, and SED

### What is AWK and GAWK

-   Awk is a powerful programming language designed for pattern scanning and processing
-   It is efficient in processing and analyzing text files, making it a staple tool in shell scripting and other data processing tasks
-   Enables users to extract, manipulate, and report on structured text data with ease
-   Then there is GAWK, which stands for GNU Awk
-   It is essentially an extension of Awk providing additional features and enhancements beyond the original AWK language
-   GAWK is often encountered ina GNU/Linux environment as the default AWK interpreter
-   Basic AWK Syntax:
    -   Print Entire Line:
        -   `awk '{print}' input.txt`
    -   Print Specific Columns:
        -   `awk '{print $1, $3}' input.txt`
    -   Calculate and Print Column Sum:
        -   `awk '{sum += $2} END {print "Sum of column 2:", sum}' input.txt`
    -   Filter and Print Lines Based on Condition
        -   `awk '$3 > 50 {print}' input.txt`
    -   Calculate and Print Average:
        -   `awk '{sum += $2} END {print "Average of column 2:", sum/NR}' input.txt`
    -   Print Lines Matching a Pattern:
        -   `awk '/pattern/ {print}' input.txt`
    -   Concatenate Columns and Print:
        -   `awk '{print $1, $2 $3}' input.txt`
    -   Conditional Printing with Pattern Matching:
        -   `awk '/pattern/ {print $1, $3}' input.txt`
-   AWK and GAWK Examples
    -   Example file:
        -   ![28](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c58de7d59417fb4c02f2283d8395fd14eba20dc9e7e66ea0c94c39e27512709dc97717253b7f1a3e00f502f9cb91.png)
    -   Display the content of a text file:
        -   `awk '{print}' sample_awk.txt`
        -   `gawk '{print}' sample_awk.txt`
        -   ![29](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/664b250a354983b6eceb28a6c2a88bb1ce62b45cf7a8d3acc1db66ee363d99e3776e2ff2908bed2c55c32b64343c.png)
    -   Extracting specific columns of a text file:
        -   `awk -F',' '{print $1, $3}' sample_awk.txt`
        -   `gawk -F',' '{print $1, $3}' sample_awk.txt`
        -   `-F` is for specifying the field separator, in this case a comma as seen in the example file
        -   ![30](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0c1c724cc77f5a28ff77aef5c65694b6f217b98ddc045b3f88306b6a33949d7fc3f716568a53457c07a65c4de076.png)
    -   Calculating the average salary:
        -   `awk -F',' '{total += $3; count++} END {print "Average Salary:", total/count}' sample_awk.txt`
        -   `gawk -F',' '{total += $3; count++} END {print "Average Salary:", total/count}' sample_awk.txt`
        -   ![31](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/eb2c189c15857d5c8086c4cdde216f4c73f4f0504b4934a8a0cb5f6c27667bbd78da9df0c417fc20ad8b18c0d0b6.png)

### What is SED

-   sed, short for stream editor, is a command-line utility in Unix and Unix-like operating systems for processing text streams
-   Its primary purpose is to perform basic text transformations on an input stream (a file or input from a pipeline) and print the results to the standard output
-   Basic sed Syntax:
    -   Substitute (Replace) Text:
        -   `sed 's/old_text/new_text/' input.txt`
    -   In-Place Editing (Modify File):
        -   `sed -i 's/old_text/new_text/' input.txt`
    -   Print Specific Line(s):
        -   `sed -n '2p' input.txt`
    -   Print Lines Matching a Pattern:
        -   `sed -n '/pattern/p' input.txt`
    -   Delete Lines Matching a Pattern:
        -   `sed '/pattern/d' input.txt`
    -   Append Text to Specific Line(s):
        -   `sed '2a\Additional line of text' input.txt`
    -   Insert Text Before Specific Line(s):
        -   `sed '2i\Inserted line of text' input.txt`
    -   Replace Specific Line(s):
        -   `sed '2c\Replaced line of text' input.txt`
-   sed Use Cases Examples
    -   Replacing text:
        -   `sed 's/George/SBT/' sample_sed.txt`
        -   This command will replace the first occurrence of the word "George" with "SBT" in each line of sample_sed.txt. However, it won't modify the original file; it will just display the modified text.
        -   ![32](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/75270cad9f2efaa0337dcb988fcc9df63e8a5516680541fe3898b49ec3134d029c24026af50ba3b2be16e30e4612.png)
    -   In-place editing (modifying the file):
        -   `sed -i 's/John/Malik/' sample_sed.txt`
        -   This command will perform an in-place edit, meaning it will modify the original file (sample_sed.txt) by replacing the first occurrence of "John" with "Malik" in each line.
        -   ![33](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/28aee051b612e8b312f3155613ffc22315a940439fcca8de9d3a9a5402f3d0bfece3d961f33916bde51cc2c53b77.png)
    -   Printing specific lines
        -   `sed -n '2p' sample_sed.txt`
        -   This command will print the second line of sample_sed.txt. The -n option suppresses automatic printing, and 2p instructs sed to print the second line.
        -   ![34](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c764c42f182b0ab1f3e1d7d9092f18300aa59b6d802dd89a99913a324b613642429580e49b12de20b9f4bfda8b2b.png)
    -   Appending text to specific lines:
        -   `sed '2a\Intro to Bash Course by SBT' sample_sed.txt`
        -   This command appends the text "Intro to Bash Course by SBT" after the second line of sample_sed.txt.

### Combining Awk and Sed

-   An example where we use both awk and sed to manipulate a text file
-   Let's say you have a file named sample_awk.txt with the following content:
    -   `Name,Age,Salary`
        `John,25,20000`
        `Yhulo,23,40000`
        `Arnold,21,22000`
        `George,32,21000`
    -   `awk -F',' 'NR == 1 {print "\t " $0} NR > 1 {print "Employee: " $0}' sample_awk.txt | sed 's/,/ /g’`
        -   `awk -F` : Sets the field separator to a comma (,). This is useful when processing CSV (Comma-Separated Values) files.
        -   `NR == 1`: Selects the first line.
        -   `{print "\t " $0}`: For the first line, it prints a tab and two spaces followed by the entire line.
        -   `NR > 1`: Selects lines with a record number greater than 1 (i.e., excludes the first line).
        -   `{print "Employee: " $0}`: For lines after the first, it prints "Employee:" followed by the entire line.
        -   `|`: The pipe operator. It takes the output from the preceding command and uses it as the input for the following command.
        -   `sed 's/,/ /g’`: Uses the sed (stream editor) command to replace all occurrences of commas (,) with spaces.
        -   So, the combined effect of these commands is to add the "Employee: " prefix starting at the second line and replace commas with space.
        -   After running this command, the output will be:
        -   ![35](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1ef95179c0ce6c8cadea47f50bd24e54d1cbbaafd7344510985ea2821df490c15cbdea2f3693929159c1bd026344.png)

### Quiz

1. What is the primary function of the SED command in Unix-like systems?
    - File compression and archiving
    - Interactive text editing
    - Stream editing
    - Binary file editing
2. Which SED command replaces the first occurrence of 'text1' with 'text2' in a file?
    - sed 's/text1/text2/' filename
    - sed 'd/text1/text2/' filename
    - sed 'r/text1/text2/' filename
    - sed 'm/text1/text2/' filename
3. Which scenario is ideal for using both AWK and SED together?
    - Using AWK for file permissions adjustments and SED for system monitoring
    - Using SED to analyze data and AWK to modify files
    - There is no practical scenario where both would be used together
    - Using AWK for complex data analysis and SED for modifying the output
4. What is a key benefit of mastering both AWK and SED?
    - Ability to efficiently process and manipulate text data within scripts
    - Improved system boot time
    - Enhanced ability to create graphical interfaces
    - Increased network security
5. What is AWK primarily used for in Unix-like systems?
    - Managing user permissions
    - System monitoring
    - Text processing and data extraction
    - Network configuration
6. How does GAWK differ from AWK?
    - GAWK is a system monitoring tool, whereas AWK is for text processing
    - GAWK is older and less efficient than AWK
    - GAWK is the GNU version of AWK, offering additional features and extensions
    - There is no difference; GAWK is just another name for AWK

## Sorting, Removing Duplicates and Column Extraction with sort, uniq, and cut

### Introduction to sort

-   The sort command is used to arrange the lines of text files or input streams in a specified order.
-   Its primary purpose is to perform sorting operations, making it a valuable tool for organizing and preparing data for further processing.
-   Sort can be applied to various data types, including numerical and textual.

-   Sort Basic Syntax
    -   Default Sorting: `sort names.txt`
        -   Command description: Without any options, sort performs lexicographical sorting, arranging lines alphabetically for text files.
    -   Numerical Sorting: `sort -n numbers.txt`
        -   Command description: The `-n` option enables numerical sorting, considering the values as numbers rather than strings.
    -   Reverse Sorting: `sort -r data.txt`
        -   Command description: The `-r` option reverses the order of sorting, arranging lines in descending order.
    -   Field-Based Sorting: `sort -t':' -k2,2 file.csv`
        -   Command description: The `-k` option allows sorting based on specific fields in a line. This command sorts a CSV file based on the second field. `-t` is the field separator
    -   Unique Sorting: `sort -u names.txt`
        -   Command description: The `-u` option removes duplicate lines while sorting.
    -   Human-Readable Sorting: `sort -h sizes.txt`
        -   Command description: The `-h` option performs human-readable sorting (e.g., 1K, 2M).
    -   Custom Delimiter: `sort -t'|' data.txt `
        -   Command description: The `-t` option specifies a custom delimiter for fields. This command sorts a file with '|' as the field delimiter.
-   Sort Use Cases:
    -   Default Sorting: `sort sample_names.txt`
        -   This sort command arrange a list of names in alphabetical order.
        -   ![28](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/54b9406fa05561729b51cb3a86abbfecd920a2fd4ba50fd542d9c2f54196bea929e8381f522536d31ccbc8009fa1.png)
    -   Numerical Sorting: `sort -n sample_numbers.txt`
        -   The -n option enables numerical sorting, considering the values as numbers rather than strings.
        -   ![29](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a220a3a33e7d9440ad9d2dc35dbdb5afd1f4c84f3a1397f08ffbb3d387dc89a1dba7ec70d25233e8e333383b6f26.png)
    -   Reverse Sorting: `sort -r sample_text.txt && sort -r sample_numbers.txt`
        -   The -r option reverses the order of sorting, arranging lines in descending order.
        -   ![30](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6702ca77e8f55e6344658920bd590475be4e4188e8c14235687ab465e3d78871d518bde8ea83ee191f000abe4082.png)
    -   Field-Based Sorting: `sort -t':' -k2,2 file.csv`
        -   The -k option allows sorting based on specific fields in a line. This command sorts a CSV file based on the described field(-k2,2).
        -   ![31](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/480fd58e5395eb9a75b8b5537dbcb9f6f9d9b72809c497f854c3a0b944b1af8fe6a055c1ba7678bf98196ad9a81b.png)
    -   Unique Sorting: `sort -u names.txt`
        -   The -u option removes duplicate lines while sorting.
        -   ![32](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f00be9957045508650097b70ae71b865e68e1dbb49e7a239d325b19d123923609f5fc2e9db47d94fb31ae47bd462.png)
    -   Human-Readable Sorting: `sort -h sizes.txt`
        -   The -h option performs human-readable sorting (e.g., 1K, 2M).
        -   ![33](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e9475e4f4842c1a259a27750a5cb8b37019de0b9e63267158e6babe02b1043b3511206cbd971e35f46d9eb7420fe.png)
    -   Custom Delimiter: `sort -t'|' data.txt`
        -   The -t option specifies a custom delimiter for fields. This command sorts a file with '|' as the field delimiter.
        -   ![34](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/01fa98933c92b710ee68aa8ade6d3c73e4a3ec6d293c25dfc7b85dcf9d6e77a4bea694c460c7390e1e832d572358.png)

### Introduction to uniq

-   uniq is a command-line utility in Unix and Unix-like operating systems designed for identifying and removing duplicate lines in a sorted text file or input stream.
-   Its primary purpose is to process adjacent matching lines and produce a unique set of lines as output.

-   Basic Syntax
    -   `uniq [options] [input_file [output_file]]`
        -   `options`: Flags to customize the behavior of uniq
        -   `input_file`: The file to be processed by uniq. If not specified, input is taken from `stdin`
        -   `output_file`: The file where the unique lines are written. If not specified, output is directed to `stdout`
    -   Removing Adjacent Duplicates: `sort data.txt | uniq`
        -   By default, uniq removes only adjacent duplicates lines, and is most effected on a sorted input
    -   Counting Duplicate Lines: `sort log.txt | uniq -c`
        -   The `-c` option provides a count of the number of occurrences for each line
    -   Ignoring Case: `sort names.txt | uniq -i`
        -   The `-i` option makes uniq case-insensitive
    -   Displaying Only Duplicates: `sort file.txt | uniq -d`
        -   The `-d` option displays only duplicate lines
-   Use Cases:
    -   Removing Adjacent Duplicates: `sort data.txt | uniq`
        -   By default, uniq removes only adjacent duplicate lines. It is most effective when used on sorted input.
        -   ![35](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fe8a24bb143c296d4edd58c77b6339d94c48baba58275d40df88b9015fa92977fbd83310e98bc40ee6ff75a42fff.png)
    -   Counting Duplicate Lines: `sort sample_log.txt | uniq -c`
        -   The `-c` option provides a count of the number of occurrences for each line.
        -   ![36](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e41f038fd0ff66b777a66b7dc578ffe24a95ca6c5b049093539dad1a7f71343136bb485b1cc24962d500441fea44.png)
    -   Ignoring Case: `sort sample_names.txt | uniq -i`
        -   The `-i` option makes uniq case-insensitive.
        -   ![37](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/972f3bf7e1f95af89da67eae5f228cbdcd62d1c503b5f566c6910ab9113f73c5a8baf1e49e7a5d6c39416421f324.png)
    -   Displaying Only Duplicates: `sort sample_duplicates.txt | uniq -d`
        -   The `-d` option displays only duplicate lines.
        -   ![38](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/581b11cba14b9b00295736c82495a4b338ed75f6b9a3f7ef1e6e1092ff94515673b0437f6ff69795979305612d83.png)

### Introduction to cut

-   cut is a command-line utility in Unix and Unix-like operating systems used for extracting sections from each line of input text files.
-   It is particularly useful for working with delimited data, where fields are separated by a specified delimiter.

-   Cut Basic Syntax:
    -   `cut [options] [file]`
        -   `options`: Flags to customize the behavior of cut
        -   `file`: The file from which to extract sections, if not specified, input is taken from stdin
    -   Specifying Delimiter: `cut -d',' -f1,3 csv_data.txt`
        -   The `-d` option allows users to specify the delimiter used in the input file. Only selects fields 1 and 3
        -   ![39](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/032ad2dd9ac1dcc8752651ba76ff6fb2a31cc217d877f95dd18fe1d4eb1aea398ce2abf4dd64ae408a628f38f91c.png)
    -   Character Position: `cut -c1-5 text.txt`
        -   Instead of specifying fields, you can also extract characters based on character position
        -   ![40](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c2b91a770cb371ed6e7476b79ef31585f4c23273cf7e8c4cf3401588bc9d2dd3e0d764334c39c34700eb31fc3c84.png)

### Combining SORT, UNIQ, and CUT

-   Pipelining
    -   Pipelining is a powerful concept in Unix-like operating systems that involves connecting the output of one command as the input to another command using the pipe (`|`) operator.
    -   This section explores the synergies between sort, uniq, and cut when used in combination through pipelining.
-   Combining sort, uniq and cut
    -   Sorting, Removing Duplicates, and Extracting Fields command:
        -   `cat sample_data.csv | sort | uniq | cut -d',' -f2,3`
        -   `cat sample_data.csv`: Reads the content of the data.csv file.
        -   `sort`: Sorts the lines in lexicographical order.
        -   `uniq`: Removes adjacent duplicate lines. cut -d',' -f2,3: Extracts the second and third fields using ',' as the delimiter.
        -   ![41](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a73aa68c77c854a4e170a8d35bdd934f5504673a227ed38791788bd21ff87d62562016e3e269646a44691e2ca9e7.png)
    -   Counting Unique Entries Command:
        -   `cut -d',' -f2 data.csv | sort | uniq -c`
        -   `cut -d',' -f2 data.csv`: Extracts the second field from data.csv.
        -   `sort`: Sorts the extracted field.
        -   `uniq` -c: Counts the occurrences of each unique entry.
        -   ![42](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/917c4505bc9129e14a0d0baec9ca88d5301b73a3c8263b7f52c32cb8a3fbc432d79d15cc155bc71e81dfe96dd7fb.png)
    -   Extracting Top N Entries Command:
        -   `cut -d',' -f3 data.csv | sort | uniq -c | sort -nr | head -n 5`
        -   `cut -d',' -f3 data.csv` |` # Extract the third field (Occupation)
        -   `sort |` # Sort the occupations alphabetically
        -   `uniq -c |` # Count the occurrences of each unique occupation
        -   `sort -nr |` # Sort the counts in descending order
        -   `head -n 5` # Display the top 5 most frequently occurring occupations
        -   ![41](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b51e5221808cb89ec9cd109f96749e84f5d2d314fa8247b7abf538af1f13f737aa27439934057df57099c5b01c5f.png)

### Quiz:

1. What does the sort command do when applied to a text file?
    - Counts the number of lines that match a pattern
    - Changes the permissions of the file
    - Displays the first ten lines of the file
    - Arranges the lines of the text file in alphabetical or numerical order ✅
2. How can you sort a file numerically using the sort command?
    - sort -p file
    - sort -c file
    - sort -n file ✅
    - sort file -n
3. Which command is used to report or omit repeated lines, usually combined with sort?
    - cut
    - uniq ✅
    - grep
    - sed
4. What is the primary use of the cut command?
    - To merge two files
    - To remove sections from each line of files ✅
    - To sort data in a file
    - To find unique lines in a file
5. How would you use the cut command to extract the first column from a file?
    - cut -d"." -f1 file
    - cut -c1 file
    - cut -d"," -f1 file ✅
    - cut -b1 file

## Writing Simple Bash Scripts

### Creating and Running Bash Scripts

-   Bash scripts are text files containing a series of Bash commands that are executed in sequence when the script is run.
-   To create a simple Bash script, you can use a text editor like nano, vim, or even a graphical editor like sublime.
-   Here's an example of a basic Bash script that displays a greeting message:
    -   ![42](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/ae70d5a4f1a5d4b300b5af2ca0df36effda76d8d6b4b39a04ac91e6253671b939e13f33be08b9c6db42207438ff7.png)
    -   `#!/bin/bash` is called the shebang line, which specifies that the script should be interpreted using the Bash shell
    -   Comments start with `#` and are for adding explanations and documentation
    -   `echo` is used to print the `"Hello, World!"` message to the terminal
    -   To run the script, save it to a file (e.g., `basicscript.sh`), make it executable with the `chmod` command (`chmod +x basicscript.sh`), and then execute it by running `./basicscript.sh`.
-   Using Shebangs (`#!/bin/bash`):
    -   The shebang line, `#!/bin/bash`, is a special command at the beginning of a Bash script that specifies the interpret, ensuring proper execution of the script
    -   Without the shebang, the system wouldn't know which interpreter to use, and the script might not work
    -   ![43](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/51e0b2ee79537becfc051de0097d856eca47ff77a0c280601a2b9c50c754ce74e1f5a1874a03010fd14b405bcb59.png)
    -   The `-p` acts as the prompt and the num is the variable that is set using user input.
    -   The `$` is used to refer to variables

### Variables and Input

-   Variables are essential for storing and manipulating data within your scripts, and accepting user input allows your scripts to be interactive
-   Accepting user input
    -   ![44](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/97edec56fdbc4cfceaac64e9e759503b4220447460d4cf66c9830ca93682cbab5eb6a33bf012abf530a3d3caea39.png)
    -   In this example, the read command is used to capture the user's name, which is then displayed in a greeting message
-   Variable Interpolation
    -   This involves embedding the value of variable within a string
    -   This is done by placing the variable name within double quotes, and its value is substituted when the string is evaluated
    -   ![45](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d84803a7b2a4d012bbf1761b14e57364782ace126a3eb781972c736e509cb5dea7453d719f598f81425ecd4bd731.png)

### Control Structures

-   Used to make decisions and implement loops
-   Conditional statements (if, else, fi):
    -   Conditional statements, such as `if` and `else`, are used to perform actions based on specific conditions
    -   The `fi` keyword marks the end of the conditional block
    -   ![46](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e8a3738a9aefe271597050f583c28b7ba2bfa18dda95c4b45db44aa6d8b6f89d21b38579d41d8442ac1876fa1735.png)
        -   The `-ge` stands for greater than or equal to
-   Loops (for, while):
    -   `for` loops iterate over a list of items, while `while` loops continue execution as long a specified condition is true
    -   ![47](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/66f42992aaacfc98298abe5abb119438d57f71362ed5b8ca8bd483e809c178ac8a64582152104b74ce70567315eb.png)
        -   This for loop example iterates over an array of fruits and prints the fruit at that iteration with the prefix `I like`
    -   ![48](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7cec7ef23c638eaaaa28ea88e9a5d57d9a85e2ce09502f5d33305df03c4f2f09ac2c9c92aca2416e7935ccbe511d.png)
        -   This while loop example updates count by 1 while the count variable is less than 5

### Quiz:

1. What is the correct extension typically used for Bash scripts?
    - .txt
    - .bash
    - .sh ✅
    - .script
2. How do you make a Bash script executable?
    - chown ubuntu scriptname
    - chmod 777 scriptname.sh
    - chmod +x scriptname.sh ✅
    - chown 755 scriptname
3. How do you read input during script execution and store it in a variable named user_input?
    - read $user_input
    - read user_input ✅
    - input user_input
    - capture user_input
4. What is the correct syntax for a conditional statement in Bash?
    - if [ condition ]: then
    - if condition [ then ]
    - if [ condition ]; then ✅
    - if then [ condition ]
5. Which control structure is used for repeating tasks a specific number of times?
    - if
    - for ✅
    - while
    - repeat
6. What is a key advantage of using Bash scripts in system administration?
    - They provide a graphical interface
    - They automate repetitive tasks ✅
    - They reduce the need for network security
    - They replace the need for manual data entry

## Scripting Advances

### Functions

-   Allows for more modular and reusable pieces of code
-   Creating and Using Functions

    -   Functions in Bash are blocks of code that perform a specific task
    -   They are defined using the `function` keyword or simply by the function name followed by parentheses
    -   A function can be called upon to execute its code
    -   ![49](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fb0b8db8eb680d72ece991bc1b2d954236f16f25771f99f1473cd54ef8774bbca993d53f3535f1d3e0d7a5bcba49.png)

-   Returns Values
    -   Functions can return values to the calling code
    -   This allows you to pass information back from the function, providing a way to convey results or data
    -   ![50](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a0b036d58510474d22f59229d46e0e7a33cd16fa8ac91986be6bb64faefaf8ba0839dd3d73ac8c08bd729182a174.png)

### Advanced Function Concepts

-   Local and Global Variables in Functions
    -   Scope of variables in functions is crucial for writing robust scripts
    -   ![51](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/bde2abee7255ca6668277ae7c22a307c728aa910d791c1e13f469c6d2fd3e295842a90e5e51c811df9decd68f7f7.png)
        -   In this example, `local_var` is a local variable inside the function, while `global_var` is a global variable accessible both inside and outside the function
-   Function Parameters and Arguments
    -   Functions can accept parameters (arguments) to make them more flexible
    -   ![52](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/44347657511840084931f84e6cff2a97e253338b9c70d4c6ee07f1cda7774aea4e5689d3def8d9e4b7e7c71fd4ae.png)
    -   Here, the `greet` function takes a parameter (`$1`) representing the name and uses it to customize the greeting messages
-   Recursive Functions
    -   These are functions that call themselves
    -   ![53](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/203c5cef8a20e3163c8ddc9e90f0a773bf00d89c8abf8434b401b0d2f671b392938519f51675de7772621670544e.png)
    -   An array named `names` is defined with a list of names.
    -   The `greet_people` function is a recursive function that greets each person in the list.
    -   The function removes the greeted person from the list and calls itself recursively to greet the next person.
    -   The script starts the recursive greeting process.

### Function Error Handling and Exit Codes

-   Handling Errors in Functions
    -   ![54](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/50882c00f64c14b14e713fd6dac4c397ec562a6e43532d1def758bdcb64adc840b93f6c99ec730310c097b5ef7c0.png)
    -   In this example, the divide function checks for a division by zero error and returns an error code if encountered
-   Exit Codes and Function Status
    -   Functions can communicate their success or failure to the calling code using exit codes.
    -   Understanding exit codes is essential for scripting in a more controlled and error-aware manner.
    -   ![55](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7f8a8dc24ad35d47555facc4aa867f251c0e6b3a0a14c3be13d28e8886606b8ccd71e7a666bed25f9ff7272b9984.png)
-   Trapping Signals in Functions
    -   Trap signals (interrupts, errors) within functions to ensure graceful termination and cleanup.
    -   ![56](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8964041310b9a4f2eda761935233881cd156993649ed7b40bbd547278f7f1bf128fb7b406041a417bbde53bf25a9.png)
        -   `.e` helps check for existence of the file
    -   In this example, the cleanup function is registered to run upon script exit, ensuring cleanup activities, right before the script terminates. The simulate_error function intentionally returns an error to demonstrate signal trapping.

### Advanced Function Techniques

-   Variable Scoping in Nested Functions
    -   ![57](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/22c1b2d6c9ccab6b01173ab4a2e6497c4414219b423a0c285c817897a66712f2dc7e61fc9f37fe5d116593804834.png)
    -   Here, the inner_function is nested within the outer_function, and variables from both scopes are accessed.
-   Dynamic Function Names
    -   Dynamically generating function names in Bash, enabling more flexible and versatile scripting.
    -   ![58](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d92d1df05d9d550309ca409b7fbddf840de6f8c5a1ffc4bb2a29a2fa44407fc0ea1e086e35ffcc745226b07c0254.png)
    -   In this example, three functions with dynamic names are created using a loop, showcasing the ability to generate functions programmatically.

### Quiz

1. What is the primary purpose of using functions in scripting?
    - To increase the script’s execution time
    - To add graphical elements to the script
    - To reduce code redundancy and simplify complex scripts ✅
    - To interact directly with the hardware
2. Which command within a function is used to return an exit status that signals an error?
    - exit 1
    - return 1 ✅
    - return 0
    - exit 0
3. Why is error handling critical in function development?
    - It allows the script to fail silently
    - it prevents the programmer from debugging
    - It ensures the script continues to operate under unexpected conditions ✅
    - It reduces the memory usage of the script
4. How can Bash functions be nested within other functions?
    - By declaring them outside the script
    - By defining one function inside another ✅
    - Using a special keyword nested
    - This is not possible in Bash

## Case Study: PCAPEXTRACT

### Automating Boring Tasks with Bash Scripting

-   PCAPEXTRACT: Packet Analysis on Steroids

    -   [PCAPEXTRACT - made by authors](https://github.com/RAB301000001C3/PCAPEXTRACT/blob/main/pcapextract)

-   Introduction to Script Overview
    -   Run the script using “./pcapextract”.
    -   Scans the current directory to look for files ending in “.pcap” file extension.
    -   Create a directory for every instances of PCAP file which the artifacts will be stored.
    -   Copy the PCAP file into the directory for cleaner execution.
    -   Checks if PCAP file exists in the directory, then run script if found, if not print the word “empty”.
-   Script Functionality Overview
    -   Shebang, Calling Functions, Display Message and Variable Declaration
        -   A script always start with shebang (#!/bin/bash) declaration followed by the display message and lastly variable declaration.
        -   Here’s the sample from PCAPEXTRACT script:
        -   Setting variables for file, date, current directory, and username
        -   ![59](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/af7ac65a8cfedb446236c8222be6006d707e4820353df52e477902ab5bc926b00d11267a1b24b58dec2321a58984.png)
    -   Variables are defined with the following values:
        -   `#!/bin/bash`: Shebang line specifies the Bash interpreter
        -   `pcapextrfunc`: Imports functions from
        -   `lolcat`: Displays a banner command.
        -   `figlet` : Displays a stylized message and applies lolcat.
        -   `file`: Assigned the string value "file".
        -   `date`: Assigned the current date in the format YYMMDD, obtained using the date command with the format option %y%m%d.
        -   `dir`: Assigned the current working directory using the pwd command.
        -   `usr`: Assigned the current user's username using the whoami command.
    -   Creating Conditional Loop
        -   For Loop:
            -   Iterates through each .pcap file in the current directory.
        -   Directory and File Handling:
            Sets the current .pcap file to the variable 'pcap'.
            Creates a new directory with the current date in the name for each .pcap file.
            Prints status messages about the directory creation and file copying.
        -   Copy Operation:
            Copies the current .pcap file to the newly created directory.
        -   Comments:
            -   Comments are included within the code using # to explain each section's purpose.
            -   Additional comments are provided outside the code block for a more detailed explanation.
        -   ![60](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/84197d7b5f8f4ab5c33095a58e31c2119a12dbe850ea2e17f0cfbcb763c0f0e991682728023ce93e74e933172063.png)
    -   Creating Conditional Loop: Extracting PCAP’s GET METHOD
        -   In this part of the script, it checks if the created directory is NOT empty then if the PCAP file is found it will continue with the analysis.
        -   ![61](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/764b662a17737a0f3eeac60fb486ac5613e53aca1353940c93363b067b215014371e5e470f92ef36d6cd1bde649f.png)
    -   The part of the script does the following:
        -   Checks if the directory for the current pcap file is not empty.
        -   If the directory is not empty, it proceeds to the next steps.
        -   Displays a message indicating the presence of the pcap file.
        -   Checks if the directory path is not empty.
        -   If the directory path is not empty, it initiates the analysis and processing steps for the pcap file.
        -   Displays messages indicating the start of the analysis and processing, incorporating sleep delays for a better user experience.
    -   Next, these commands are used to perform actions from a PCAP file. We used TSHARK a command line counterpart of Wireshark which is famous as network packet analysis tool to extract HTTP.GET Method found inside the pcap file.
        -   ![62](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/97ad0df549d19f32a804279d21088cb34826c95351f2f298fe78df8f8f1c709528c5cffb6b070617013e832391d7.png)
    -   This script does the following:
        -   Runs tshark commands for HTTP analysis on the pcap file.
        -   Writes the results of the tshark commands to corresponding output files within a dated directory.
        -   Indicates the completion of the extraction process.
    -   Capture and Filter HTTP Requests with User-Agent "curl":
        -   `“tshark -t ad -r ${pcap##/} -Y 'http.user_agent contains "curl" and http.request.method == GET' > ${pcap##/}.$date/${pcap##/}.$date.GET.txt*”`
            -   Analyze network traffic from the specified .pcap file.
            -   Applies a display filter to include only HTTP requests where the User-Agent contains "curl" and the request method is GET.
            -   Redirects the filtered output to a text file with a specific naming convention in a directory based on the original .pcap file and the current date.
    -   Append Separator Line to the Output File:
        -   `“echo "******************************* " >> ${pcap##/}.$date/${pcap##/}.$date.GET.txt”***`
            -   Appends a separator line to the same text file to distinguish different sections of output.
    -   Capture All HTTP Requests:
        -   `“tshark -t ad -r ${pcap##/} -Y 'http.request.method == GET' >> ${pcap##/}.$date/${pcap##/}.$date.GET.txt”*`
            -   Analyze all HTTP requests from the same .pcap file.
            -   Appends the output to the text file mentioned earlier.
    -   Capture All HTTP Traffic:
        -   `“tshark -t ad -r ${pcap##/} -Y "http" > ${pcap##/}.$date/${pcap##/}.$date.HTTP.txt”*`
            -   Analyze all HTTP traffic from the .pcap file.
                Redirects the output to a separate text file in a directory with the specified naming convention.
    -   Export HTTP Objects:
        -   `“tshark -Q -r ${pcap##/} --export-objects http,${pcap##/}.$date/${pcap##/}.$date.EXPORT”*`
            -   Exports HTTP objects from the .pcap file, such as images or files transferred over HTTP.
            -   Saves the exported objects in a directory with a specific naming convention.
    -   Capture and Sort Source and Destination IP Addresses with Ports:
        -   `“tshark -r ${pcap##/} -T fields -e ip.src -e tcp.srcport -e ip.dst -e tcp.dstport | sort -t: -u -k1,1 > ${pcap##/}.$date/${pcap##/}.$date.IP_PORTS.txt”*`
            -   Captures and extracts source and destination IP addresses with corresponding ports.
            -   Sorts and removes duplicate entries based on the source IP address.
    -   Print Extraction Completion Status:
        -   `echo -e "\t Status: Extraction Complete" echo -e "\t Extracting IP ADDRESSES"`
            -   Prints a status message indicating that the extraction process is complete.

### Automating IP Addresses Extraction

-   This segment of the script is designed to extract IP addresses from a PCAP file using grep, utilizing a regular expression that matches the IP address format.
-   The primary purpose of this script section is to extract and organize IP addresses from text files generated by preceding commands.
-   `echo -e "\t Status: Extraction Complete"`
-   `echo -e "\t Extracting IP ADDRESSES" grep -ohE "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b" ${pcap##/}.$date/${pcap##/}.$date..txt | sort -t: -u -k1,1 | gawk 'BEGIN {print "SORTED IP ADDRESSES \n"} {print $0}' > ${pcap##/}.$date/${pcap##/}.$date.IPSORTED.txt`
-   `echo `
-   `echo "************************ Extracting IP Address(es) found: View full extracted IP Addresses at ${pcap##/}.$date directory **************************** "`
-   `sleep .5`
-   `head -n1 ${pcap##/}.$date/${pcap##/}.$date.IPSORTED.txt | tail -n8 ${pcap##/}.$date/${pcap##*/}.$date.IPSORTED.txt`
-   `echo "********************************************************************************************"`
-   `echo " "`
-   ![63](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e51d0f2ac04cf286e9221c74760fc343a84f666567b3568432ede1c29e011f70da996b430aabc6cf68fbd84a5ea8.png)
-   `echo -e "\t Extracting IP ADDRESSES”`
    -   Outputs a message indicating that the script is initiating the extraction of IP addresses.
-   Extract and Sort IP Addresses:
    -   `grep -ohE "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b" ${pcap##/}.$date/${pcap##/}.$date..txt | sort -t: -u -k1,1 | gawk 'BEGIN {print "SORTED IP ADDRESSES \n"} {print $0}' > ${pcap##/}.$date/${pcap##/}.$date.IPSORTED.txt*`
        -   Utilizes grep to search for and extract IP addresses from text files with a specific naming pattern.
        -   Applies sorting and removes duplicate IP addresses based on the first field using sort.
        -   Prepend a header to the sorted IP addresses using gawk.
        -   Redirects the sorted IP addresses to a new text file.
    -   Print and Pause Execution
        -   `echo echo "************************* Extracting IP Address(es) found: View full extracted IP Addresses at ${pcap##/}.$date directory **************************** "**`
        -   `sleep .5`
        -   Outputs a blank line to enhance visual separation.
        -   Displays a status message indicating that IP addresses have been successfully extracted and directs the user to a specific directory.
        -   Delays the script execution for half a second, improving readability.
    -   Display Part of the Extracted IP Addresses:
        -   `head -n1 ${pcap##/}.$date/${pcap##/}.$date.IPSORTED.txt | tail -n8 ${pcap##/}.$date/${pcap##/}.$date.IPSORTED.txt`
        -   Utilizes head and tail commands to exhibit the first line (header) and the subsequent eight lines of the sorted IP addresses.
        -   Offers a preview of the extracted IP addresses.
    -   Print blank line and Separator
        -   `echo "***************************************************************************************" echo " "`
        -   Outputs a separator line for visual clarity.
        -   Outputs a blank line for enhanced visual separation in the console.

### Automating DNS Extraction

-   ![64](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/32ecabb4baf6e08583a015f01f9afd3ecc6f0b77cdf9e3145e6ea8310fc961d7a04105b2f390cdbabd4ef5acfead.png)
-   Print Message:
    -   `echo -e "\t Extracting Domain Names Found: View full extracted domains at ${pcap##/}.$date directory”\*`
        -   Outputs a message indicating that the script is about to extract domain names.
-   Capture DNS Traffic:
    -   `tshark -t ad -r ${pcap##/} -Y 'udp.port == 53' > ${pcap##/}.$date/${pcap##/}.$date.Domain_Names_Raw.txt\*`
        -   Uses tshark to capture DNS traffic (UDP port 53) from the PCAP file.
        -   Redirects the raw output to a text file in a directory with a specific naming convention.
-   Filter DNS Traffic:
    -   `cat ${pcap##/}.$date/${pcap##/}.$date.Domain_Names_Raw.txt | dnsfilter > ${pcap##/}.$date/${pcap##/}.$date.Domain_Names_Filtered.txt`
    -   Applies a function “dnsfilter” from “pcapextrfunc” to print DNS in human readable format.
    -   Here’s the sample function:
    -   ![65](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b4ffbeb6f40a6c156b106618bfeb5211c6afcdf5e45c6452d297dd8bc38e13dca6158dac32ab59812cd153a868af.png)
    -   `function dnsfilter {`
        `gawk 'BEGIN { print " " print "No. \t Time \t \t \t \t IP.SRC \t IP.DEST \t DNS.QRY" print " \t " } { print $1 " " $2 " " $3 " " $4 " " $5 " " $6 " " $13 } '`
        `}`
    -   Redirects the filtered output to another text file.
-   Display the First 10 Lines of Filtered Domain Names:
    -   `cat ${pcap##/}.$date/${pcap##/}.$date.Domain_Names_Filtered.txt | head -n10 2> /dev/null`
    -   Uses cat and head to display the first 10 lines of the filtered domain names.
    -   Redirects potential errors to /dev/null.
    -   Pause
        -   `sleep .5`
        -   Introduces a short delay in script execution for better readability.
    -   Remove Raw Domain Names File:
        -   `rm ${pcap##/}.$date/${pcap##/}.$date.Domain_Names_Raw.txt`
        -   Deletes the raw domain names file to save space and maintain cleanliness
    -   Capture and Sort Unique Domain Names:
        -   `tshark -r ${pcap##/} -T fields -e ip.src -e dns.qry.name -2R "dns.flags.response eq 0" | awk -F" " '{ print $2 }' | sort -u 2> /dev/null 1> ${pcap##/}.$date/${pcap##/}.$date.Domain_Names_LIST.txt*`
        -   Uses tshark to capture DNS query names and source IP addresses for non-response DNS traffic.
        -   Uses awk to extract the domain names.
        -   Sorts and removes duplicates from the list.
        -   Redirects errors to /dev/null and saves the unique domain names to another text file.
    -   Print Separator and Blank Lines
        -   `echo " " echo "**********************************************************************************" echo " "`
        -   Outputs a separator line and a blank line for clear visual demarcation.

### Automating Hostname Extraction

-   ![66](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5ebab166a3ae700e0bdd424bf37b9c0ec9b316bb612deae8f3cfac0c9d8c6e106b5120c8fbaf58f317cb732fe34f.png)
-   Print Message:
    -   `echo -e "\t Extracting Host Names Found: View full extracted Hostnames at ${pcap##/}.$date directory"\*`
        -   Outputs a message indicating that the script is about to extract hostnames.
    -   Pause Execution:
    -   `sleep .5`
        -   Introduces a short delay in script execution for better readability.
    -   Capture Kerberos CNameString Information:
    -   `tshark -t ad -r ${pcap##/} -C pcapextract -Y "kerberos.CNameString" | awk -F" " '{ print $1,$2,$3,$4,$5,$6,$9}' | cname > ${pcap##/}.$date/${pcap##/}.$date.HOSTNAMES.txt\*`
        -   Uses tshark to capture Kerberos CNameString information from the PCAP file.
        -   Uses awk to extract specific fields (timestamp, source and destination IP addresses, and the Kerberos CNameString itself).
        -   Redirects the output to a text file using a function called cname.
        -   Here’s the code snippet for function cname to make the output readable
        -   ![67](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5ac1c03326bc0db02dee1c5de97d422ac3d5d3d1872a171b20ed7eaacce3b7ffc44236f073bbd6c9e168dddbb974.png)
    -   Pause Execution and Display the First 5 Lines of Hostnames:
        -   `sleep .5 head -n5 ${pcap##/}.$date/${pcap##/}.$date.HOSTNAMES.txt`
            -   Introduces another short delay in script execution for better readability.
            -   Uses head to display the first 5 lines of the extracted hostnames.
        -   Print Blank and Separator
        -   `echo echo "**************************************************************************************" echo`
            -   Outputs a blank line for enhanced visual separation.
            -   Outputs a separator line for clear visual demarcation.
            -   Outputs a blank line for further visual clarity.

### Automating Export File Hashing

-   ![68](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0bd2fdd6cee309f5b4a474614c36b6971aca96d2c195c3302c5ce5f98c45e242d50f3a622dc5f2c46f16ee8cf683.png)
-   Path and Variable Setup:
    -   `z="${pcap##/}.$date/${pcap##/}.$date.EXPORT"`
        -   This line creates a variable z by constructing a path based on the current pcap file (${pcap##\*/}) and the current date.
-   Search for file with \*.PDF extension:
    -   `*pdf=$(find $dir -name .pdf)`
        -   Searches for files with a ".pdf" extension in the directory specified by $dir and assigns the result to the variable pdf.
-   Export Directory Handling:
    -   `if [ -n $z ]`
    -   Checks if the export path (z) is non-empty.
    -   If non-empty:
        -   Changes the current directory to z.
        -   Outputs messages indicating the extraction of hash values.
        -   Executes the hash command and formats the output.
        -   Changes the current directory back to the original directory.
    -   `hash | sed 'N;s/\\n/ /'`
-   Executes the hash function and uses sed to replace newline characters with spaces in the output.
-   Here’s the sample code snippet for hash function:
-   ![69](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7eb6b54c90a6a3f926c6ca1aaadb289edc6b86b2f933e3275da3a6cc15bc088447e185e2c9b18df5144427549bd4.png)
-   If empty, outputs "Export Directory is empty."
    Conditional Processing:

    -   `else`
        -   `echo "Export Directory is empty"`
    -   `fi`

-   `else`
    -   `echo "No GET method found"`
-   `fi`
-   `else`
-   `echo "empty"`
-   `fi`

-   Handles nested conditional statements:
    -   If there is a GET method in the pcap file, it processes the file, extracts various information (IP addresses, domain names, etc.), and prints the results.
    -   If there is no GET method, it outputs "No GET method found."
    -   If the pcap file is empty, it outputs "empty."

### Quiz ☠️

1. Did you have fun learning how Scripting can help you in your daily tasks? Click "YES" to complete

-   `Yes`

2. Did you have fun learning how Scripting can automate 'Boring Tasks'? Type "YES" to complete

-   `YES`
