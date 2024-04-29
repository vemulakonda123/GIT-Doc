## creating method or function to call in script for multiple time
```
#!/bin/bash
clear
read_input()            ## read_input is a function or method , calling that function into program
{
               read -p "Enter first number: " num1
               read -p "Enter second number: " num2
}

echo "---------------------------------"
echo "-------Welcom to Calculator------"
echo "---------------------------------"
echo -e "[a]addition\n[b]substraction\n[c]multiplication\n[d]division\n"
read -p "Enter your choise: " choise
case $choise in
        [aA])
                read_input
                result=$((num1+num2))
                echo "The result for your choise is: $result"
                ;;
        [bB])
                read_input
                result=$((num1-num2))
                echo "The result for your choise is: $result"
                ;;
        [cC])
                read_input
                result=$((num1*num2))
                echo "The result for your choise is: $result"
                ;;
        [dD])
               read_input
                result=$((num1/num2))
                echo "The result for your choise is: $result"
                ;;
        *)
                echo "wrong choise"
                ;;
```
