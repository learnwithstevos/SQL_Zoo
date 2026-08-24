### 1) List the teachers who have NULL for their department.
```sql
SELECT teacher.name FROM teacher
LEFT JOIN dept ON teacher.dept = dept.id
WHERE teacher.dept IS NULL
```

### 2) Note the INNER JOIN misses the teachers with no department and the departments with no teacher.
```sql
SELECT teacher.name, dept.name
FROM teacher INNER JOIN dept
ON (teacher.dept=dept.id)
```

### 3) Use a different JOIN so that all teachers are listed.
```sql
SELECT teacher.name, dept.name FROM teacher
LEFT JOIN dept ON teacher.dept = dept.id
```

### 4) Use a different JOIN so that all departments are listed.
```sql
SELECT teacher.name, dept.name FROM teacher
RIGHT JOIN dept ON teacher.dept = dept.id
```

### 5) Use a different JOIN so that all departments are listed.
```sql
SELECT teacher.name,COALESCE(teacher.mobile, '07986 444 2266') AS mobile
FROM teacher 
```