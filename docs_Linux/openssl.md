# OpenSSL

## Generate Private Key
```
openssl genpkey -algorithm RSA -out <key name>.key -pkeyopt rsa_keygen_bits:2048
```

## Generate Certificate Signing Request
```
openssl req -new -key <key name>.key -out <csr name>.csr
```

## Generate Server Certificate
```
openssl req -new -x509 -key <key name>.key -out <certificate name>.crt -days 365 -addext "subjectAltName=DNS:<host name>,IP:<IP address>"
```

