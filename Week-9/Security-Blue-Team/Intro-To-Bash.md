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
