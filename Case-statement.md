## Case statement
```
#!/bin/bash
clear
echo "---------------------------------"
echo "-------Welcom to Calculator------"
echo "---------------------------------"
echo -e "[a]addition\n[b]substraction\n[c]multiplication\n[d]division\n"
read -p "Enter your choise: " choise
case $choise in
        [aA])
                read -p "Enter first number: " num1
                read -p "Enter second number: " num2
                result=$((num1+num2))
                echo "The result for your choise is: $result"
                ;;
        [bB])
                read -p "Enter first number: " num1
                read -p "Enter second number: " num2
                result=$((num1-num2))
                echo "The result for your choise is: $result"
                ;;
        [cC])
                read -p "Enter first number: " num1
                read -p "Enter second number: " num2
                result=$((num1*num2))
                echo "The result for your choise is: $result"
                ;;
        [dD])
                read -p "Enter first number: " num1
                read -p "Enter second number: " num2
                result=$((num1/num2))
                echo "The result for your choise is: $result"
                ;;
        *)
                echo "wrong choise"
                ;;
        esac
```
## output::
```
---------------------------------
-------Welcom to Calculator------
---------------------------------
[a]addition
[b]substraction
[c]multiplication
[d]division

Enter your choise: D
Enter first number: 88
Enter second number: 22
The result for your choise is: 4
```

