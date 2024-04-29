## sed command
```
cat only used to see the content of a file.
but sed command can do more without opening file

 sed sed-comm.txt
  349  sed '' sed-comm.txt
  351  sed 'p' sed-comm.txt   ## p ==prints double time
  354  sed -n 'p' sed-comm.txt   ## by adding -n it will print only single time
  356  sed -n '$p' sed-comm.txt		## $p prints last line
  357  sed -n '5,8p' sed-comm.txt	## prints 5-8 line from file
  358  cat sed-comm.txt		
  360  sed -n '$p' sed-comm.txt
  361  sed '$p' sed-comm.txt
  362  sed -n '$p' sed-comm.txt
  363  sed '10d' sed-comm.txt			## d to delete 10 line
  364  sed '5,11p' sed-comm.txt			## print 5-11 line
  365  sed -n '5,11p' sed-comm.txt
  366  sed -n '5,11d' sed-comm.txt		## delete 5-11 line, not permently
  367  cat sed-comm.txt
  368  sed '5,11d' sed-comm.txt
  369  cat sed-comm.txt
  370  sed -i '2,4d' sed-comm.txt			## delete 2-4 line permently  ## -i used to replace actual file
  371  ls
  372  cat sed-comm.txt
  373  sed -i.back '5,7d' sed-comm.txt		## backuping actual file while deleting
  374  cat sed-comm.txt
  375  cat sed-comm.txt.back
  376  cat sed-comm.txt
  359  cat passwd.back	
  377  sed 's/root/devops/' passwd.back		## Here root was (s) substuited with devops of first line
  378  sed 's/nologin/devops/' passwd.back	## Here nologin was (s) substuited with devops of first line	
  379  cat passwd.back
  380  sed 's/nologin/devops/g' passwd.back	## Here nologin was (s) substuited with devops of all lines (g) globally	
  381  sed -i 's/nologin/devops/g' passwd.back	## Here nologin was (s) substuited with devops of all lines permently(i)
  382  cat passwd.back
  383  cat passwd.back
  384  sed '/usr/s/devops/linux/g' passwd.back
  385  sed '1i -----------------' sed-comm.txt		## adding content at line1
  386  sed '4i -----------------' sed-comm.txt		## adding content at line4
  387  cat sed-comm.txt
  388  sed -i '4i -----------------' sed-comm.txt		## adding content at line4 	## -i permently replace
  389  cat sed-comm.txt
  390  sed -i '10a ############## ' sed-comm.txt	## adding content at line10	## -i permently replace
  391  cat sed-comm.txt
```
