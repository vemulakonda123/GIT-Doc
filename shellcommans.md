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

