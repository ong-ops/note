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

- Common flaws in Authentication
  - Brute force attacks
  - Use of weak credentials
  - Weak Session Cookies
  - Add a space at first when register existing username
- Mitigation
  - To avoid password-guessing attacks
  - To avoid brute force attacks
  - Implement MFA

## 8. Software and Data Integrity Failures

- Checksum (MD5, SHA1, SHA256)
  - md5sum
  - sha1sum
  - sha256sum
- 2 Type vulnerabilities
  - **Software Integrity Failure**
    - No check against the 3rd party lib/software
    - Use the `Subresource Integrity (SRI)` to specify a hash along the lib URL so that the lib code is executed only if the hash downloaded file matches the expected value (https://www.srihash.org/)
    - The correct way to insert lib in HTML code
    ```html
    <script src="https://code.jquery.com/jquery-3.6.1.min.js" integrity="sha256-o88AwQnZB+VDvE9tvIXrMQaPlFFSUTR+nldQm1LuPXQ=" crossorigin="anonymous"></script>
    ```
  - **Data Integrity Failure**
    - Cookie
    - https://appdevtools.com/base64-encoder-decoder
    - Use `JWT` to prevent alter Cookie by a user
      - `JWT` and the `None` Algorithm
        - Attacker can bypass the signature validatino by changing 2 things in JWT
          1. Modify the header section `alg` contain the value `none`
          2. Remove the signature part
          3. Remain last dot

## 9. Security Logging & Monitoring Failures



## 10. Server-Side Request Forgery (SSRF)



