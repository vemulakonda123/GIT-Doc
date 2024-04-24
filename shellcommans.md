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

