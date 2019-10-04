

# OJT Session 5 - Advanced SQL Injection 


##What is SQL Injection

SQL injection (SQLI) is a technique that allows a user to inject SQL commands into the database engine from a vulnerable application. By leveraging the syntax and capabilities of SQL, the attacker can influence the query passed to the back-end database in order to extract sensible information. SQL injection can be done anywhere a database is used and user input is not sanitized correctly.


### Types of SQL Injection 

		Inband SQL Injection
			-Error Based Injection
			-Union Based Injection
		Blind Injection
			-Boolean Based Injection
			-Time based Injection
		
		
### Order of SQL Injection

SQL Injection Orders 

| Order 			|		Explanation
|---			| ---  |
| First Order 		| 	attacker inserts and get the data in same query	|
| Second order 		|	Where attacker inserts a payload and will execute query in another portion	|
| Lateral Injection	 | Injection happens after multiple injections	|
