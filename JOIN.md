### 1) Modify it to show the game, team, player, gtime for all goals scored by player 'Leandro Trossard'
```sql
SELECT game,team,player,gtime
FROM goal 
WHERE player = 'Leandro Trossard'
```

### 2) Show the id, teamname and coach for the team with code 'BEL'
```sql
SELECT id, teamname, coach
FROM team
WHERE id = 'BEL'
```

### 3) Show the player, gtime and teamname for every goal with goal time (gtime) less than 8 minutes.
```sql
SELECT player, gtime, teamname
FROM goal JOIN team ON goal.team=team.id
WHERE gtime < 8
```

### 4) Show the player, teamname and coach for every goal scored by a team with coach named 'Sébastien'
```sql
SELECT player, teamname, coach
FROM goal JOIN team ON goal.team=team.id
WHERE coach LIKE 'Sébastien%'
```

### 5) For each goal by 'Harry Edward Kane' show the player, the game id and the city
```sql
SELECT player,game.id,city
FROM goal JOIN game ON goal.game=game.id
WHERE player = 'Harry Edward Kane'
```

### 6) List the player and team (short code) for every goal scored in 'Vancouver'
```sql
SELECT player, team
FROM goal JOIN game ON goal.game=game.id
WHERE city = 'Vancouver'
```

### 7) List the player and the teamname for every goal scored in 'Vancouver'
```sql
SELECT player, teamname
FROM goal JOIN team ON goal.team=team.id
JOIN game ON goal.game=game.id
WHERE city = 'Vancouver'
```

### 8) For each team playing on 2026-07-01, show the city and the teamname
```sql
SELECT  game.city, team.teamname
FROM game
JOIN team ON team.id = game.team1 OR team.id = game.team2
WHERE game.played = '2026-07-01'
```

### 9) For every goal scored on '2026-07-02' show the teamname, and the player who scored
```sql
SELECT team.teamname, goal.player
FROM goal JOIN team ON goal.team=team.id
JOIN game ON goal.game=game.id
WHERE game.played = '2026-07-02'
```

### 10) For every goal scored in Mexico City show the date played, the player and that player's position (pos)
```sql
SELECT game.played, goal.player, player.pos 
FROM goal 
JOIN game ON goal.game = game.id 
JOIN player ON goal.player = player.playername 
WHERE city = 'Mexico City';
```

### 10) For each goal scored by a defender, show the player, their teamname.
```sql
SELECT game.played, goal.player, player.pos 
FROM goal 
JOIN game ON goal.game = game.id 
JOIN player ON goal.player = player.playername 
WHERE city = 'Mexico City';
```

### 11) For each goal scored by a defender, show the player, their teamname.
```sql
SELECT goal.player, team.teamname
FROM goal
JOIN team ON player.team = team.id
JOIN player ON player.playername = goal.player
WHERE player.pos='DEF' 
```

### 12) For each goal scored in extra time, show the player, their position, teamname and city
```sql
SELECT DISTINCT goal.player, player.pos, team.teamname, game.city FROM goal 
JOIN player ON goal.player = player.playername
JOIN team ON player.team = team.id
JOIN game ON game.id = goal.game
WHERE goal.gtime BETWEEN 91 AND 120
```
