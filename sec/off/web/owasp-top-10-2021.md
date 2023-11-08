# OWASP Top 10 2021

## 1. Broken Access Control

### Impact

- Being able to view sensitive information from other users
- Accessing unauthorized functionality

### Attack

- Insecure Direct Object Reference (IDOR)

## 2. Cryptographic Failures

- Misuse or lack of use of cryptographic algorithms for protecting sentitive info

### Impact

- Web apps accidentally divulging sensitive data. (data directly to customer or technical info)

### Attack

- MITM

### Example

#### Access to the database

- Scenario: Use the Flat-file database (SQLite)
- Use `sqlite3` to access a Flat-file database
- `sqlite3 <database-name>` Connect to the database file
- `.tables` Show the tables in the database
- `PRAGMA table_info(<table-name>)` Show the table info
- `SELECT * FROM customer;` dump the info from the table

#### Cracking the password

```
sqlite> SELECT * FROM customers;
0|Joy Paulson|4916 9012 2231 7905|5f4dcc3b5aa765d61d8327deb882cf99
1|John Walters|4671 5376 3366 8125|fef08f333cc53594c8097eba1f35726a
2|Lena Abdul|4353 4722 6349 6685|b55ab2470f160c331a99b8d8a1946b19
3|Andrew Miller|4059 8824 0198 5596|bc7b657bd56e4386e3397ca86e378f70
4|Keith Wayman|4972 1604 3381 8885|12e7a36c0710571b3d827992f4cfe679
5|Annett Scholz|5400 1617 6508 1166|e2795fc96af3f4d6288906a90a52a47f
```
- Use the online tool: https://crackstation.net/


## 3. Injection



## 4. Insecure Design



## 5. Security Misconfiguration



## 6. Vulnerable and Outdated Components



## 7. Identification and Authentication Failures



## 8. Software and Data Integrity Failures



## 9. Security Logging & Monitoring Failures



## 10. Server-Side Request Forgery (SSRF)



