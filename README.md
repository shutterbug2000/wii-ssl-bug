tl;dr Versions of Wii IOS before IOS37 (which was also when Trucha was fixed) will ignore certain errors in SSL certs, treating them as valid.
This is used by [Wiimmfi](https://wiimmfi.de/) as of May 20th, 2021.


As a basic guide to create a compatible cert, you:
- Generate a cert and key with OpenSSL, using a 1024 bit key
- Convert the cert .pem to .der (raw) form
- Towards the end (the signature portion) find and change `05 00 03 81 81` to `04 00 03 81 81`
- Convert back to .pem (base64) form
- Install on your webserver
