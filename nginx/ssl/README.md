# SSL Certificates

## how to create SSL certificate

###Install openssl

Refer the [Official Documentation](https://github.com/openssl/openssl#download)

###Create Certificate

```bash
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout nginx-selfsigned.key -out nginx-selfsigned.crt
```
####Understanding the Command above

 - openssl: This is the basic command line tool for creating and managing OpenSSL certificates, keys, and other files.
 - req: This subcommand specifies that you want to use X.509 certificate signing request (CSR) management. The “X.509” is a public key infrastructure standard that SSL and TLS adheres to for its key and certificate management. You want to create a new X.509 cert, so you are using this subcommand.
 - x509: This further modifies the previous subcommand by telling the utility that you want to make a self-signed certificate instead of generating a certificate signing request, as would normally happen.
 - nodes: This tells OpenSSL to skip the option to secure your certificate with a passphrase. You need Nginx to be able to read the file, without user intervention, when the server starts up. A passphrase would prevent this from happening because you would have to enter it after every restart.
 - days 365: This option sets the length of time that the certificate will be considered valid. You set it for one year here.
 - newkey rsa:2048: This specifies that you want to generate a new certificate and a new key at the same time. You did not create the key that is required to sign the certificate in a previous step, so you need to create it along with the certificate. The rsa:2048 portion tells it to make an RSA key that is 2048 bits long.
 - keyout: This line tells OpenSSL where to place the generated private key file that you are creating.
 - out: This tells OpenSSL where to place the certificate that you are creating.