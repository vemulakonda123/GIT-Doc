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

## Here we using disk_utilization()	function to re use it
```
#!/bin/bash
echo "Here we are implementing functions"

disk_utilization()		# this is a function
{
disk=`df -h`
echo "disk utilization is : $disk  "
}

if [[ $?  -eq  0 ]];
then 
	echo "this is disk usage"
	disk_utilization		## above function was called
else
	echo "disk has some issue to print"
fi
```
