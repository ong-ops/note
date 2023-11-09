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

- Use the online tool: https://crackstation.net/ for weak hashed

## 3. Injection

- SQL Injection
- Command Injection
  - Execute inline command `$(your_command_here)`

## 4. Insecure Design

- Insecure Password Resets
  - Rate limit only 1 ip
  - Predicable Question like colour

## 5. Security Misconfiguration

- Poorly configured permission on cloud services (S3 bucket)
- Having unnecessary features enabled (services, pages, accounts or privileges)
- Default accounts with unchanged password
- Error messages that are overly detailed and allow attackers to find out more about the system.
- Not using HTTPs
- Debugging features in production software

## 6. Vulnerable and Outdated Components



## 7. Identification and Authentication Failures



## 8. Software and Data Integrity Failures



## 9. Security Logging & Monitoring Failures



## 10. Server-Side Request Forgery (SSRF)



