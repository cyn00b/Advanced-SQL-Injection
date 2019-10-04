#SQL Demo

Table : Movies

|	Id	|	Title	|	Director	|	Year	|	Length_minutes	|
|	---	|	---	|	---	|	---	|	---	|
|	1	|	Toy Story	|	John Lasseter	|	1995	|	81	|
|	2	|	A Bug's Life	|	John Lasseter	|	1998	|	95	|
|	3	|	Toy Story 2	|	John Lasseter	|	1999	|	93	|
|	4	|	Monsters, Inc.	|	Pete Docter	|	2001	|	92	|
|	5	|	Finding Nemo	|	Andrew Stanton	|	2003	|	107	|
|	6	|	The Incredibles	|	Brad Bird	|	2004	|	116	|
|	7	|	Cars	|	John Lasseter	|	2006	|	117	|
|	8	|	Ratatouille	|	Brad Bird	|	2007	|	115	|
|	9	|	WALL-E	|	Andrew Stanton	|	2008	|	104	|
|	10	|	Up	|	Pete Docter	|	2009	|	101	|
|	11	|	Toy Story 3	|	Lee Unkrich	|	2010	|	103	|
|	12	|	Cars 2	|	John Lasseter	|	2011	|	120	|
|	13	|	Brave	|	Brenda Chapman	|	2012	|	102	|
|	14	|	Monsters University	|	Dan Scanlon	|	2013	|	110	|


###SELECT QUERY 


FROM

```
SELECT title, director FROM movies; 
```

ID
 
```
SELECT id, title FROM movies WHERE id = 6;
```

BETWEEN

```
SELECT title, year FROM movies WHERE year BETWEEN 2000 AND 2010;
```

<>

```
SELECT title, year FROM movies WHERE year < 2000 OR year > 2010;
```

<=

```
SELECT title, year FROM movies WHERE year <= 2003;
```

LIKE

```
SELECT title, director FROM movies WHERE title LIKE "Toy Story%";
```

VALUE = *

```
SELECT title, director FROM movies WHERE director = "John Lasseter";
```

VALUE !=

```
SELECT title, director FROM movies WHERE director != "John Lasseter";
```

_

```
SELECT * FROM movies WHERE title LIKE "WALL-_";
```

LIMIT

```
SELECT title, year FROM movies ORDER BY year DESC LIMIT 4;
```

ORDER BY

```
SELECT DISTINCT director FROM movies ORDER BY director ASC;
```

OFFSET 

```
SELECT title FROM movies ORDER BY title ASC LIMIT 5 OFFSET 5;
```


##Another Table 

Table Name : Boxoffice

|	Movie_id	|	Rating	|	Domestic_sales	|	International_sales	|
|	---	|	---	|	---	|	---	|
|	5	|	8.2	|	380843261	|	555900000	|
|	14	|	7.4	|	268492764	|	475066843	|
|	8	|	8	|	206445654	|	417277164	|
|	12	|	6.4	|	191452396	|	368400000	|
|	3	|	7.9	|	245852179	|	239163000	|
|	6	|	8	|	261441092	|	370001000	|
|	9	|	8.5	|	223808164	|	297503696	|
|	11	|	8.4	|	415004880	|	648167031	|
|	1	|	8.3	|	191796233	|	170162503	|
|	7	|	7.2	|	244082982	|	217900167	|
|	10	|	8.3	|	293004164	|	438338580	|
|	4	|	8.1	|	289916256	|	272900000	|
|	2	|	7.2	|	162798565	|	200600000	|
|	13	|	7.2	|	237283207	|	301700000	|


JOIN

```
SELECT title, domestic_sales, international_sales FROM movies  JOIN boxoffice ON movies.id = boxoffice.movie_id ;
```

JOIN ORDER BY

```
SELECT title, rating FROM movies  JOIN boxoffice ON movies.id = boxoffice.movie_id ORDER BY rating DESC;
```

COUNT(*)

```
SELECT director, COUNT(*) as Num_movies_directed FROM movies GROUP BY director;
```

COUNT id 

```
SELECT director, COUNT(id) as Num_movies_directed FROM movies GROUP BY director;
```


##UPDATE 

```
UPDATE movies SET director = "John Lasseter“ WHERE id = 2;
```

### INSERT 

```
INSERT INTO movies VALUES (4, "Toy Story 4", "El Directore", 2015, 90);
```


