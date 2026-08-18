### 1) List the films where the yr is 1962 and the budget is over 2000000 [Show id, title]
```sql
SELECT id, title
FROM movie
WHERE yr=1962 AND budget > 2000000
```

### 2) Give year of 'Citizen Kane'.
```sql
SELECT yr FROM movie
WHERE title = 'Citizen Kane'
```

### 3) List all of the Star Trek movies, include the id, title and yr (all of these movies start with the words Star Trek in the title). Order results by year.
```sql
SELECT id, title, yr FROM movie
WHERE title LIKE 'Star Trek%'
```

### 4) What id number does the actor 'Glenn Close' have?
```sql
SELECT actor.id FROM actor
WHERE actor.name = 'Glenn Close'
```

### 5) What is the id of the 1942 film 'Casablanca'
```sql
SELECT movie.id FROM movie
WHERE movie.title = 'Casablanca'
```

### 6) Obtain the cast list for 1942's 'Casablanca'.
```sql
SELECT actor.name FROM movie
JOIN casting ON movie.id = casting.movieid
JOIN actor ON actor.id = casting.actorid
WHERE movie.title = 'Casablanca' 
AND movie.id = 11768 AND movie.yr = 1942
```

### 7) Obtain the cast list for the film 'Alien'
```sql
SELECT actor.name FROM movie
JOIN casting ON movie.id = casting.movieid
JOIN actor ON actor.id = casting.actorid
WHERE movie.title = 'Alien'
```

### 8) List the films in which 'Harrison Ford' has appeared
```sql
SELECT movie.title FROM movie
JOIN casting ON movie.id = casting.movieid
JOIN actor ON actor.id = casting.actorid
WHERE actor.name = 'Harrison Ford'
```

### 9) List the films where 'Harrison Ford' has appeared - but not in the starring role. [Note: the ord field of casting gives the position of the actor. If ord=1 then this actor is in the starring role]
```sql
SELECT movie.title FROM movie
JOIN casting ON movie.id = casting.movieid
JOIN actor ON actor.id = casting.actorid
WHERE actor.name = 'Harrison Ford' AND casting.ord != 1
```


### 10) List the films together with the leading star for all 1962 films.
```sql
SELECT movie.title, actor.name FROM movie
JOIN casting ON movie.id = casting.movieid
JOIN actor ON actor.id = casting.actorid
WHERE movie.yr = 1962 AND casting.ord = 1
```

### 11) Which were the busiest years for 'Rock Hudson', show the year and the number of movies he made each year for any year in which he made more than 2 movies.
```sql

```


