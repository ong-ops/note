# MySQL (Port 3306)

- A relational database management system (RDBMS) based on Structured Query Language (SQL)
- Used a client-server model
- Many other products (PostgreSQL, Microsoft SQL server)
- https://dev.mysql.com/doc/dev/mysql-server/latest/PAGE\_SQL\_EXECUTION.html

## RDBMS

- A software or service are used to create and manage databases based on a relational model.
- The word `relational` means the data stored in the dataset is organised as tables.

## How does MySQL work?

- The server handles all database instructions like creating, editing, accessing data.
- It takes and manages these requests and communicates using the MySQL protocol.
- MySQL stages:
  1. MySQL creates a database for storing and manipulating data, defining the relationship of each table
  2. Clients make requests by making specific statements in SQL
  3. The server will respond to the client with whatever info has been requested

## Enumerate

Install MySQL Client to connect to the remote MySQL server
```
sudo apt install default-mysql-client
```

Manually enumerate MySQL by Nmap script (https://nmap.org/nsedoc/scripts/mysql-enum.html)
Or Perl script (https://www.exploit-db.com/exploits/23081)
```
nmap --script mysql-enum -p 3306 <ip>
```

Connect to the MySQL server
```
mysql -h <ip> -u <username> -p
```

Enumerate using Metasploit (Module: `auxiliary/admin/mysql/mysql_sql`)
```
msfconsole
use mysql_sql
```

## Exploitation

Dump database using Metasploit (Module: `auxiliary/scanner/mysql/mysql_schemadump`)
```
msfconsole
use mysql_schemadump
```

Dump hash using Metasploit (Module: `auxiliary/scanner/mysql/mysql_hashdump`)
```
msfconsole
use mysql_hashdump
```

## Cracking password

Using John the Ripper
```
john hash.txt
```
