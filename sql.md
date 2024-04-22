## 2つのカラムを指定してIN句を使用する
```SQL
SELECT *
FROM users
WHERE (first_name, last_name) IN (('John', 'Doe'), ('Jane', 'Smith'));
```
