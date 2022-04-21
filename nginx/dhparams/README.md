# DH Params

###Install openssl

Refer the [Official Documentation](https://github.com/openssl/openssl#download)

###Create Certificate

```bash
sudo openssl dhparam -out nginx/dhparams/dhparam.pem 2048
```