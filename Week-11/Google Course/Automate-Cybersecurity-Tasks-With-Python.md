# Automate Cybersecurity Tasks With Python

## Module 1

### Data Types in Python

#### String
- **Definition:** Data consisting of ordered sequence of characters.
- **Characters:** May include letters, numbers, symbols, and spaces.
- **Format:** Characters must be placed within quotation marks.

#### List
- **Definition:** Data structure consisting of collection of data in sequential form.
- **Elements:** Can be of any data type (strings, integers, Booleans, or other lists).
- **Format:** Elements placed within square brackets, separated by commas.

#### Integer
- **Definition:** Data consisting of number that does not include decimal point.

#### Float
- **Definition:** Data consisting of number with decimal point.

#### Boolean
- **Definition:** Data that can only be one of two values: True or False.
- **Important:** Should not place Boolean values in quotation marks.

#### Tuple
- **Definition:** Data structure consisting of collection of data that cannot be changed.
- **Elements:** Can contain elements of varying data types like lists.
- **Key difference:** Possible to change elements in list, but not possible to change elements in tuple.
- **Cybersecurity use:** Useful when software identifiers stored in tuple to ensure they will not be altered.
  - Provides assurance that access control list will only block intended software.
- **Memory efficiency:** Tuples are more memory efficient than lists, useful when working with large quantity of data.

#### Dictionary
- **Definition:** Data consisting of one or more key-value pairs.
- **Structure:** Each key mapped to value with colon (:) between key and value.
- **Format:** Commas separate key-value pairs, dictionary placed within curly brackets ({}).
- **Use:** Useful when want to store and retrieve data in predictable way.
- **Example:** Dictionary maps building name to number with building name as value and number as key.

#### Set
- **Definition:** Data consisting of unordered collection of unique values.
- **Uniqueness:** No two values in set can be same.
- **Format:** Elements placed within curly brackets and separated by comma.
- **Elements:** Can be of any data type.

#### Infinite Loops
- **Definition:** Loop that doesn't exit.
- **Stopping method:** Press CTRL-C or CTRL-Z on keyboard to stop infinite loop.
- **Use case:** May need to do this when running service that constantly processes data (e.g., web server).

## Module 2

### Use Function Parameters

#### Function Parameters Overview
- **Parameters:** Variables defined in function definition that function depends on.
- **Arguments:** Data brought into function when it is called.
- **Example:** range() function uses parameters for start and stop indices accepting integer values.

#### Single Parameter Function
- **Definition:** Function with one parameter placed inside parentheses.
- **Example:** `greet_employee(name)` function with name parameter.
- **Usage:** Print welcome message using name variable passed into function.
- **Calling:** Call function with specific argument (e.g., `greet_employee("Charley Patel")`).

#### Multiple Parameters
- **Definition:** Function can have more than one parameter separated by commas.
- **Example:** `greet_employee(first_name, last_name)` with two parameters.
- **Calling:** Include two arguments separated by comma when calling function.
- **Usage:** `greet_employee("Kiara", "Carter")` to greet someone with first and last name.

### Global and Local Variables

#### Global Variables
- **Definition:** Variable available through entire program, assigned outside function definition.
- **Access:** Can be called inside or outside functions, returns assigned value.
- **Example:** `device_id = "7ad2130bd"` assigned at beginning of code.
- **Usage:** Can access and modify throughout code in conditionals, loops, functions, and other syntax.

#### Local Variables
- **Definition:** Variable assigned within function, cannot be called or accessed outside function body.
- **Scope:** Include parameters and other variables assigned within function definition.
- **Example:** In `def greet_employee(name):`, both `total_string` and `name` are local variables.
- **Lifetime:** Python creates variables temporarily while function runs and deletes them from memory after function stops.
- **Error:** Using local variable outside function will cause error.

#### Best Practices
- **Naming:** Use variable name only once, even if one defined globally and other locally.
- **Global access:** Functions can access values of global variables.
- **Parameter preference:** Better to use parameter instead of global variable for passing different values.
- **Name reuse:** Reusing global variable name within function creates new local variable with same name.
- **Complexity:** Best to avoid combining global and local variables within functions due to complexity.

### Modules and Libraries

#### Built-in Functions
- **Definition:** Come standard with every version of Python.
- **Examples:** `print()`, `type()`, `max()`, and many more.
- **Access:** To access additional pre-built functions, import a library.

#### Libraries and Modules
- **Library:** Collection of modules that provide code users can access in their programs.
- **Module:** Python file containing additional functions, variables, classes, and runnable code.
- **Structure:** All libraries generally made up of several modules.
- **Purpose:** Help save programmers time and make code more readable.

#### Python Standard Library
- **Definition:** Extensive collection of usable Python code that often comes packaged with Python.
- **Security modules:**
  - `re` module: Useful for searching patterns in log files
  - `csv` module: Allows efficient work with CSV files
  - `glob` and `os` modules: For interacting with command line
  - `time` and `datetime`: For working with timestamps

#### External Libraries
- **Access:** Can download external libraries beyond Python Standard Library.
- **Examples:**
  - Beautiful Soup: For parsing HTML website files
  - NumPy: For arrays and mathematical computations
- **Security use:** Assist in network traffic analysis, log file parsing, and complex math.

## Module 3

### Regular Expressions in Python

#### Regex Overview
- **Definition:** Regular expression (regex) is sequence of characters that forms pattern.
- **Use:** Can search for any kind of pattern within log files.
- **Examples:** Find strings starting with certain prefix or strings of certain length.
- **Security context:** Can find all IP addresses with specific network ID (e.g., 184).

#### Regex Symbols

##### Plus Sign (+)
- **Function:** Represents one or more occurrences of specific character.
- **Example:** Pattern `a+` matches string of any length where "a" is repeated.
- **Matches:** Single "a", three "a's", five "a's", or even 1000 "a's" in row.

##### \w Symbol
- **Function:** Matches any alphanumeric character but doesn't match symbols.
- **Examples:** "1", "k", "i" are examples of what `\w` matches.
- **Combination:** `\w+` matches alphanumeric string of any length.
- **Flexibility:** `\w` provides flexibility in alphanumeric characters, plus sign provides flexibility in string length.

#### Email Address Extraction
- **Challenge:** Need to extract email addresses from log without knowing specific emails.
- **Solution:** Use regex to tell Python how email address is structured.
- **Email format:** `user1@email1.com` with segments separated by @ symbol and period.
- **Regex pattern:** `\w+@\w+\.\w+`
  - First `\w+`: Alphanumeric characters of varying length (username)
  - `@`: Always present @ symbol
  - Second `\w+`: Domain name with alphanumeric characters
  - `\.`: Period (backslash needed because period has special meaning in regex)
  - Third `\w+`: Final part (com, net, etc.)

#### Python Implementation
- **Import:** Use `re` module for regular expressions in Python.
- **Function:** `re.findall()` returns list of matches to regular expression.
- **Usage:** `re.findall(pattern, string)` where pattern is regex in quotes and string is where to search.

#### Basics of Regular Expressions

##### Regex Overview
- **Definition:** Regular expression (regex) is sequence of characters that forms pattern.
- **Use:** Can search for variety of patterns including IP addresses, emails, or device IDs.
- **Import:** Need to import `re` module first with `import re`.
- **Storage:** Regular expressions stored in Python as strings.

##### re.findall() Function
- **Function:** Returns list of matches to regular expression.
- **Parameters:** Requires two parameters.
  - First: String containing regular expression pattern
  - Second: String to search through
- **Example:** `re.findall("ts", "tsnow, tshah, bmoreno")` returns `['ts', 'ts']`.

##### Regular Expression Symbols

###### Symbols for Character Types
- **\w:** Matches any alphanumeric character (also matches underscore _).
- **.:** Matches all characters, including symbols.
- **\d:** Matches all single digits [0-9].
- **\s:** Matches all single spaces.
- **\.:** Matches the period character.

###### Symbols to Quantify Occurrences
- **+ symbol:** Represents one or more occurrences of specific character.
  - Example: `\d+` finds matches to one or more occurrences of single digit.
- **\* symbol:** Represents zero, one, or more occurrences of specific character.
  - Example: `\d*` finds matches to zero, one, or more occurrences of single digit.

