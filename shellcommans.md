### echo commands
```
#!/bin/bash
echo "hi this is shell"
echo $BASH
echo $PWD
echo $HOME
value=1
echo $value
echo $VALUE #not possible to fetch
```
### reading values from cli 
```
#!/bin/bash
>> How to read the value from cli
echo "Enter my name :"
read name1
echo "my name is: $name1"
```
### reading multiple values from cli
```
>> How to read multiple values
#!/bin/bash
echo "Entering multile names"
read nam2 nam3 nam4
echo "Names : $nam2 , $nam3 , $nam4"
```
### read passwd and hidd
```

#!/bin/bash
read -p 'username : ' user_val  # -p represent one same line we can give the value or char
read -sp 'password : ' pass_val # -s to hidd passwd
echo
echo "username : $user_val"
echo "passwd : $pass_val"

```
## read array of values 
```
#!/bin/bash
#>> How to read array value
echo "Enter names: "
read -a names
echo "${names[0]},${names[1]} .... "

```
## without read varliables we can can print value from $REPLY 
```
#!/bin/bash
echo "Enter value : "
read
echo "here your provided variable but you can see that value or char "
echo "$REPLY"
```
## argument
```
#!/bin/bash
# arguments
echo $1 $2 $3 ' > echo $1 $2 $3 '
```
## array of arguments and shortcuts
```
#!/bin/bash
# arguments
#echo $1 $2 $3 ' > echo $1 $2 $3 '
args=("$@")
echo ${args[0]} ${args[1]} ${args[2]}
echo $@
echo $#
```
## list of string comparision and integer comparision for condition statement
```
In shell scripting, you can compare both strings and integers using different operators. Here's a list of commonly used comparison operators for both string and integer comparisons:

### String Comparison Operators:

1. **Equality**:
   - `=`: Checks if two strings are equal.
   - Example: `[ "$str1" = "$str2" ]`

2. **Inequality**:
   - `!=`: Checks if two strings are not equal.
   - Example: `[ "$str1" != "$str2" ]`

3. **Non-empty**:
   - `-n`: Checks if a string is non-empty.
   - Example: `[ -n "$str" ]`

4. **Empty**:
   - `-z`: Checks if a string is empty.
   - Example: `[ -z "$str" ]`

### Integer Comparison Operators:

1. **Equal**:
   - `-eq`: Checks if two integers are equal.
   - Example: `[ "$num1" -eq "$num2" ]`

2. **Not Equal**:
   - `-ne`: Checks if two integers are not equal.
   - Example: `[ "$num1" -ne "$num2" ]`

3. **Greater Than**:
   - `-gt`: Checks if the first integer is greater than the second.
   - Example: `[ "$num1" -gt "$num2" ]`

4. **Greater Than or Equal To**:
   - `-ge`: Checks if the first integer is greater than or equal to the second.
   - Example: `[ "$num1" -ge "$num2" ]`

5. **Less Than**:
   - `-lt`: Checks if the first integer is less than the second.
   - Example: `[ "$num1" -lt "$num2" ]`

6. **Less Than or Equal To**:
   - `-le`: Checks if the first integer is less than or equal to the second.
   - Example: `[ "$num1" -le "$num2" ]`

### Notes:

- In shell scripting, `[` and `]` are used for conditional tests. They are also provided by the `test` command.
- Always quote variables (e.g., `"$str"`, `"$num"`) to handle cases where the variable may be empty or contain spaces.
- Integer comparisons should be done within double square brackets `[[ ... ]]` for more flexibility and robustness.

These operators allow you to perform conditional tests in shell scripts based on string or integer values.
```
## Examples

1. **Simple "if" statement**:
   
```bash
#!/bin/bash

# Define a variable
number=10

# Check if the number is greater than 5
if [ $number -gt 5 ]; then
    echo "The number is greater than 5."
fi
```

2. **"if-else" statement**:

```bash
#!/bin/bash

# Define a variable
age=18

# Check if the age is greater than or equal to 18
if [ $age -ge 18 ]; then
    echo "You are eligible to vote."
else
    echo "You are not eligible to vote."
fi
```

3. **"if-elif-else" statement**:

```bash
#!/bin/bash

# Define a variable
score=75

# Check the grade based on the score
if [ $score -ge 90 ]; then
    echo "Grade: A"
elif [ $score -ge 80 ]; then
    echo "Grade: B"
elif [ $score -ge 70 ]; then
    echo "Grade: C"
elif [ $score -ge 60 ]; then
    echo "Grade: D"
else
    echo "Grade: F"
fi
```

4. **Nested "if" statement**:

```bash
#!/bin/bash

# Define variables
num1=10
num2=20

# Check if num1 is greater than 5
if [ $num1 -gt 5 ]; then
    echo "num1 is greater than 5."
    
    # Check if num2 is greater than 15
    if [ $num2 -gt 15 ]; then
        echo "num2 is greater than 15."
    else
        echo "num2 is not greater than 15."
    fi
fi
```
![image](https://github.com/vemulakonda123/GIT-Doc/assets/50296141/b9d578e5-9893-4719-90bf-60f2443cd7c9)


These examples demonstrate various ways to use "if" conditions in shell scripting to make decisions based on different conditions.


## Disk space filtering
```
#!/bin/bash
disk_space=`df -h|grep "/dev/root"|awk '{print $5}'|cut -d '%' -f1`
echo "$disk_space"
if [ $disk_space -gt 50 ];
then
        echo "$disk_space is more than 50%"
elif [ $disk_space -lt 50 ];
then
        echo "$disk_space is less than 50%"
else
        echo "nothing"
fi
```
## selectcing machine and install git 
```
#!/bib/bash
echo "script to install git "
if ["$(uname)" == "linux"];
than 
	echo "this is linux mechin, installing git"
	yum install git -y
elif [ "$(uname)" == "Darwin" ];
than
	echo "this is macos"
	brew install git
else
	echo "not installing"
fi
```
## print highest utlized directory
```
du -h /home/ubuntu|sort -hr|head -1
```
## 
![image](https://github.com/vemulakonda123/GIT-Doc/assets/50296141/2c754a49-8aaf-4eb9-aefc-1c1ce3ef01f1)
## $1
myscript.sh
```
#!/bin/bash
echo "The first argument is: $1"
```
When you run this script from the command line and provide an argument, like so:
```
./myscript.sh argument1
```
output:::  The first argument is: argument1
## $1 $2
Let's modify the myscript.sh script to display both the first and second arguments:
```
#!/bin/bash
echo "The first argument is: $1"
echo "The second argument is: $2"
```
```
./myscript.sh argument1 argument2
```
output:::: 
```
The first argument is: argument1
The second argument is: argument2
```
### $0
```
In shell scripting, $0 represents the name of the script itself or the name of the function
#!/bin/bash
echo "The name of this script is: $0"
=================================
./myscript.sh
=================================
The name of this script is: ./myscript.sh
```
## $@
print_args.sh
```
In shell scripting, $@ represents all the positional parameters passed to the script or function as separate quoted strings.
#!/bin/bash
echo "All arguments passed to the script:"
echo "$@"
==========
./print_args.sh arg1 arg2 arg3
=========
All arguments passed to the script:
arg1 arg2 arg3
```
## $#
count_args.sh
```
In shell scripting, $# represents the number of positional parameters passed to the script
#!/bin/bash
echo "Number of arguments passed to the script: $#"
=======================
./count_args.sh arg1 arg2 arg3
===============
Number of arguments passed to the script: 3
```
## $$
In shell scripting, $$ represents the process ID (PID) of the current shell instance.
```
#!/bin/bash
echo "The process ID of this shell script is: $$"
===========
./script.sh
==============
The process ID of this shell script is: 12345
```
## $?
In shell scripting, $? represents the exit status of the last command that was executed
```
#!/bin/bash
ls non_existent_file.txt
echo "Exit status of 'ls' command: $?"
================
ls: cannot access 'non_existent_file.txt': No such file or directory
Exit status of 'ls' command: 2
```
In this example, ls is used to list a file (non_existent_file.txt) that does not exist.
When you run this script, the ls command will fail, and $? will hold a non-zero value corresponding to the failure.
The output will be something like:
























