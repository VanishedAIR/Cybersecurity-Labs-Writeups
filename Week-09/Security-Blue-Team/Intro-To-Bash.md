# Introduction to Bash PT2 - Advanced Text Processing (Security Blue Team)

## Text Processing

### Combining AWK and SED

You can chain these tools for powerful text processing pipelines:

```
Input: awk -F',' 'NR==1 {print "\t"$0} NR>1 {print "Employee:", $0}' data.csv | sed 's/,/ /g'
Output:
    Name Age Salary
Employee: John 25 50000
Employee: Alice 30 65000
Employee: Bob 28 55000
```

This command:

1. Uses AWK to add "Employee:" prefix to data rows
2. Pipes the output to SED to replace commas with spaces
3. Creates a formatted, readable output, GAWK, and SED

-   `awk -F` : Sets the field separator to a comma (,). This is useful when processing CSV (Comma-Separated Values) files.
-   `NR == 1`: Selects the first line.
-   `{print "\t " $0}`: For the first line, it prints a tab and two spaces followed by the entire line.
-   `NR > 1`: Selects lines with a record number greater than 1 (i.e., excludes the first line).
-   `{print "Employee: " $0}`: For lines after the first, it prints "Employee:" followed by the entire line.
-   `|`: The pipe operator. It takes the output from the preceding command and uses it as the input for the following command.
-   `sed 's/,/ /g’`: Uses the sed (stream editor) command to replace all occurrences of commas (,) with spaces.
-   So, the combined effect of these commands is to add the "Employee: " prefix starting at the second line and replace commas with space.

### AWK and GAWK - Pattern Processing Tools

AWK is a programming language designed for processing structured text data - think CSV files, and logs

**Key Concepts:**

-   AWK processes text line-by-line and field-by-field
-   Fields are referenced as `$1`, `$2`, `$3`, etc. (`$0` = entire line)
-   Built-in variables: `NR` (line number), `NF` (number of fields)
-   Perfect for data extraction and mathematical operations on text

**Basic AWK Operations:**

```
# Display entire file
Input: awk '{print}' data.txt
Output: (shows all lines in file)

# Extract specific columns (field 1 and 3)
Input: awk '{print $1, $3}' data.txt
Output: (shows only columns 1 and 3)

# Calculate sum of column 2
Input: awk '{sum += $2} END {print "Total:", sum}' numbers.txt
Output: Total: 150

# Filter lines based on condition
Input: awk '$3 > 50 {print}' scores.txt
Output: (shows only lines where column 3 > 50)
```

**AWK with CSV Data Example:**

Given a CSV file with employee data:

```
Name,Age,Salary
John,25,50000
Alice,30,65000
Bob,28,55000
```

```
# Extract names and salaries
Input: awk -F',' '{print $1, $3}' employees.csv
Output:
Name Salary
John 50000
Alice 65000
Bob 55000

# Calculate average salary (skip header)
Input: awk -F',' 'NR>1 {total += $3; count++} END {print "Average:", total/count}' employees.csv
Output: Average: 56667
```

### SED - Stream Editor

SED is a stream editor for filtering and transforming text on-the-fly. Perfect for find-and-replace operations and text modifications.

**Essential SED Operations:**

```
# Basic text replacement
Input: sed 's/old/new/' file.txt
Output: (replaces first occurrence of 'old' with 'new' on each line)

# Replace all occurrences (global)
Input: sed 's/old/new/g' file.txt
Output: (replaces all occurrences of 'old' with 'new')

# In-place editing (modifies original file)
Input: sed -i 's/John/Jane/g' file.txt
Output: (file is permanently modified)

# Print specific lines
Input: sed -n '2,5p' file.txt
Output: (shows only lines 2 through 5)

# Delete lines containing pattern
Input: sed '/pattern/d' file.txt
Output: (removes all lines containing 'pattern')

# Append text after specific line
Input: sed '2a\New line of text' file.txt
Output: (adds "New line of text" after line 2)
```

**SED Use Cases:**

-   Configuration file modifications
-   Log file cleaning and processing
-   Batch text replacements
-   Data format conversions

### Quiz: Text Processing

1. What is the primary function of the SED command in Unix-like systems?

    - Stream editing ✅
    - File compression and archiving
    - Interactive text editing
    - Binary file editing

2. Which SED command replaces the first occurrence of 'text1' with 'text2' in a file?

    - sed 's/text1/text2/' filename ✅
    - sed 'd/text1/text2/' filename
    - sed 'r/text1/text2/' filename
    - sed 'm/text1/text2/' filename

3. Which scenario is ideal for using both AWK and SED together?

    - Using AWK for complex data analysis and SED for modifying the output ✅
    - Using AWK for file permissions adjustments and SED for system monitoring
    - Using SED to analyze data and AWK to modify files
    - There is no practical scenario where both would be used together

4. What is a key benefit of mastering both AWK and SED?

    - Ability to efficiently process and manipulate text data within scripts ✅
    - Improved system boot time
    - Enhanced ability to create graphical interfaces
    - Increased network security

5. What is AWK primarily used for in Unix-like systems?

    - Text processing and data extraction ✅
    - Managing user permissions
    - System monitoring
    - Network configuration

6. How does GAWK differ from AWK?
    - GAWK is the GNU version of AWK, offering additional features and extensions ✅
    - GAWK is a system monitoring tool, whereas AWK is for text processing
    - GAWK is older and less efficient than AWK
    - There is no difference; GAWK is just another name for AWK

## Data Organization with sort, uniq, and cut

### SORT - Organizing Data

The `sort` command arranges lines of text in alphabetical or numerical order - essential for data organization and analysis.

**Key Sort Options:**

```
# Basic alphabetical sorting
Input: sort names.txt
Output: (arranges lines alphabetically)

# Numerical sorting
Input: sort -n numbers.txt
Output: (sorts numbers properly: 1, 2, 10, 20 not 1, 10, 2, 20)

# Reverse order
Input: sort -r data.txt
Output: (sorts in descending order)

# Field-based sorting (CSV)
Input: sort -t',' -k2,2 employees.csv
Output: (sorts by second column using comma delimiter)

# Remove duplicates while sorting
Input: sort -u duplicates.txt
Output: (sorts and removes duplicate lines)

# Human-readable sorting (file sizes)
Input: sort -h sizes.txt
Output: (properly sorts 1K, 2M, 1G)
```

### UNIQ - Removing Duplicates

The `uniq` command identifies and removes duplicate adjacent lines - most effective when combined with `sort`.

**Key UNIQ Operations:**

```
# Remove duplicate lines (must be sorted first)
Input: sort data.txt | uniq
Output: (shows only unique lines)

# Count occurrences of each line
Input: sort log.txt | uniq -c
Output:
    3 Error: File not found
    1 Warning: Low memory
    2 Info: Process completed

# Show only duplicates
Input: sort data.txt | uniq -d
Output: (shows only lines that appear more than once)

# Case-insensitive duplicate removal
Input: sort names.txt | uniq -i
Output: (treats "John" and "john" as duplicates)
```

### CUT - Extracting Columns

The `cut` command extracts specific fields (columns) or character ranges from text files - perfect for processing CSV data.

**Key CUT Operations:**

```
# Extract specific fields from CSV
Input: cut -d',' -f1,3 employees.csv
Output: (shows only columns 1 and 3 using comma delimiter)

# Extract character ranges
Input: cut -c1-5 text.txt
Output: (shows first 5 characters of each line)

# Extract multiple non-consecutive fields
Input: cut -d':' -f1,3,5 /etc/passwd
Output: (extracts fields 1, 3, and 5 using colon delimiter)

# Extract from specific character to end of line
Input: cut -c10- file.txt
Output: (shows characters from position 10 to end of line)
```

### Combining SORT, UNIQ, and CUT

These commands are incredibly powerful when chained together with pipes:

```
# Clean data and extract specific columns
Input: cat data.csv | sort | uniq | cut -d',' -f2,3
Output: (sorts, removes duplicates, then extracts columns 2 and 3)

# Count unique entries in specific column
Input: cut -d',' -f2 employees.csv | sort | uniq -c
Output:
    3 Engineering
    2 Marketing
    1 HR

# Find top 5 most common values
Input: cut -d',' -f3 data.csv | sort | uniq -c | sort -nr | head -5
Output: (extracts column 3, counts occurrences, sorts by count descending, shows top 5)
```

**Data Processing Pipeline Example:**
Given a log file with user access data, extract the most frequent users:

```
Input: cut -d' ' -f1 access.log | sort | uniq -c | sort -nr | head -10
Output:
   45 user123
   32 admin
   28 guest
   21 user456
   (shows top 10 most active users)
```

### Quiz: Data Organization

1. What does the sort command do when applied to a text file?

    - Arranges the lines of the text file in alphabetical or numerical order ✅
    - Counts the number of lines that match a pattern
    - Changes the permissions of the file
    - Displays the first ten lines of the file

2. How can you sort a file numerically using the sort command?

    - sort -n file ✅
    - sort -p file
    - sort -c file
    - sort file -n

3. Which command is used to report or omit repeated lines, usually combined with sort?

    - uniq ✅
    - cut
    - grep
    - sed

4. What is the primary use of the cut command?

    - To remove sections from each line of files ✅
    - To merge two files
    - To sort data in a file
    - To find unique lines in a file

5. How would you use the cut command to extract the first column from a CSV file?
    - cut -d"," -f1 file ✅
    - cut -d"." -f1 file
    - cut -c1 file
    - cut -b1 file

## Bash Scripting Fundamentals

### Creating and Running Scripts

Bash scripts are text files containing commands that execute in sequence - perfect for automating repetitive tasks.

**Basic Script Structure:**

```bash
#!/bin/bash
# This is a comment
echo "Hello, World!"
```

**Key Elements:**

-   `#!/bin/bash` - Shebang line specifies the interpreter
-   `#` - Comments for documentation
-   Commands execute line by line

**Making Scripts Executable:**

```
Input: chmod +x script.sh
Input: ./script.sh
Output: Hello, World!
```

### Variables and User Input

Variables store data and make scripts dynamic and interactive.

**Variable Examples:**

```bash
#!/bin/bash
name="John"
age=25
echo "Hello, $name! You are $age years old."

# User input
read -p "Enter your name: " user_name
echo "Welcome, $user_name!"
```

**Input/Output Example:**

```
Input: ./greeting.sh
Enter your name: Alice
Output: Welcome, Alice!
```

### Control Structures

Control structures enable decision-making and repetition in scripts.

**Conditional Statements:**

```bash
#!/bin/bash
read -p "Enter your age: " age

if [ $age -ge 18 ]; then
    echo "You are an adult"
else
    echo "You are a minor"
fi
```

**Loop Examples:**

```bash
# For loop
for fruit in apple banana orange; do
    echo "I like $fruit"
done

# While loop
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    count=$((count + 1))
done
```

**Example Output:**

```
Input: ./age_check.sh
Enter your age: 25
Output: You are an adult

Input: ./fruit_loop.sh
Output:
I like apple
I like banana
I like orange
```

### Quiz: Bash Scripting

1. What is the correct extension typically used for Bash scripts?

    - .sh ✅
    - .txt
    - .bash
    - .script

2. How do you make a Bash script executable?

    - chmod +x scriptname.sh ✅
    - chown ubuntu scriptname
    - chmod 777 scriptname.sh
    - chown 755 scriptname

3. How do you read input during script execution and store it in a variable named user_input?

    - read user_input ✅
    - read $user_input
    - input user_input
    - capture user_input

4. What is the correct syntax for a conditional statement in Bash?

    - if [ condition ]; then ✅
    - if [ condition ]: then
    - if condition [ then ]
    - if then [ condition ]

5. Which control structure is used for repeating tasks a specific number of times?

    - for ✅
    - if
    - while
    - repeat

6. What is a key advantage of using Bash scripts in system administration?
    - They automate repetitive tasks ✅
    - They provide a graphical interface
    - They reduce the need for network security
    - They replace the need for manual data entry

## Advanced Bash Scripting

### Functions - Modular Code

Functions make scripts more organized and reusable by creating blocks of code that perform specific tasks.

**Basic Function Syntax:**

```bash
#!/bin/bash

# Function definition
greet() {
    echo "Hello, $1!"
    echo "Welcome to our system."
}

# Function call
greet "Alice"
greet "Bob"
```

**Functions with Return Values:**

```bash
#!/bin/bash

calculate_sum() {
    local num1=$1
    local num2=$2
    local result=$((num1 + num2))
    echo $result  # Return the result
}

result=$(calculate_sum 5 3)
echo "Sum: $result"
```

**Example Output:**

```
Input: ./greet_script.sh
Output:
Hello, Alice!
Welcome to our system.
Hello, Bob!
Welcome to our system.

Input: ./calculator.sh
Output: Sum: 8
```

### Advanced Function Concepts

**Variable Scope and Error Handling:**

```bash
#!/bin/bash

# Function with local and global variables
process_data() {
    local input=$1
    global_counter=$((global_counter + 1))

    if [ -z "$input" ]; then
        echo "Error: No input provided" >&2
        return 1
    fi

    echo "Processing: $input"
    return 0
}

# Initialize global variable
global_counter=0

# Function calls with error checking
if process_data "file1.txt"; then
    echo "Success! Counter: $global_counter"
else
    echo "Function failed"
fi
```

**Error Handling Example:**

```bash
divide() {
    if [ $2 -eq 0 ]; then
        echo "Error: Division by zero" >&2
        return 1
    fi
    echo $(($1 / $2))
    return 0
}

# Usage with error checking
if result=$(divide 10 2); then
    echo "Result: $result"
else
    echo "Division failed"
fi
```

**Function Parameters and Arguments:**
Functions accept parameters to make them flexible and reusable:

```bash
#!/bin/bash
greet() {
    echo "Hello, $1!"  # $1 is the first parameter
    echo "You are $2 years old."
}

greet "Alice" "25"
```

**Recursive Functions:**
Functions that call themselves for repetitive operations:

```bash
#!/bin/bash
names=("Alice" "Bob" "Charlie")

greet_people() {
    if [ ${#names[@]} -eq 0 ]; then
        return
    fi

    echo "Hello, ${names[0]}!"
    names=("${names[@]:1}")  # Remove first element
    greet_people  # Recursive call
}

greet_people
```

Example Output:

```
Input: ./recursive_greet.sh
Output:
Hello, Alice!
Hello, Bob!
Hello, Charlie!
```

### Function Error Handling and Exit Codes

**Error Handling in Functions:**

```bash
#!/bin/bash
divide() {
    if [ $2 -eq 0 ]; then
        echo "Error: Division by zero" >&2
        return 1  # Error exit code
    fi
    echo $(($1 / $2))
    return 0  # Success exit code
}

# Usage with error checking
if result=$(divide 10 2); then
    echo "Result: $result"
else
    echo "Division failed"
fi
```

**Exit Codes and Function Status:**

-   `return 0` = Success
-   `return 1-255` = Error codes
-   Use `$?` to check last function's exit status

**Signal Trapping:**

```bash
#!/bin/bash
cleanup() {
    echo "Cleaning up temporary files..."
    rm -f /tmp/script_temp.*
}

trap cleanup EXIT  # Run cleanup on script exit

simulate_error() {
    [ -e "nonexistent_file" ] || return 1
}
```

This ensures graceful cleanup even when errors occur.

### Advanced Function Techniques

**Variable Scoping in Nested Functions:**

```bash
#!/bin/bash
outer_function() {
    local outer_var="Outer scope"

    inner_function() {
        local inner_var="Inner scope"
        echo "$outer_var and $inner_var"
    }

    inner_function
}

outer_function
```

**Dynamic Function Names:**

```bash
#!/bin/bash
# Create multiple functions programmatically
for action in start stop restart; do
    eval "service_${action}() { echo 'Service ${action}ing...'; }"
done

service_start
service_stop
service_restart
```

Example Output:

```
Input: ./dynamic_functions.sh
Output:
Service starting...
Service stopping...
Service restarting...
```

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

This creates a nested conditional structure that handles different PCAP file states appropriately.

### Quiz ☠️

1. Did you have fun learning how Scripting can help you in your daily tasks? Click "YES" to complete

    - ✅ `Yes`

2. Did you have fun learning how Scripting can automate 'Boring Tasks'? Type "YES" to complete
    - ✅ `YES`
