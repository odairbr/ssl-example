# ssl-example
SSL certificate study

## Generate certificate

- server certificate
```shell
openssl req -x509 \
            -sha256 -days 365 \
            -nodes \
            -newkey rsa:2048 \
            -subj "/CN=localhost/C=BR/ST=São Paulo/L=São Paulo/O=Test SSL" \
            -keyout certificates/localhost.key -out certificates/localhost.crt
```

- client certificate
```shell
openssl req -x509 \
            -sha256 -days 365 \
            -nodes \
            -newkey rsa:2048 \
            -subj "/CN=client/C=BR/ST=São Paulo/L=São Paulo/O=Client SSL" \
            -keyout certificates/client.key -out certificates/client.crt
```

## Requests

- with TLS is needed only server certificate
```shell
curl --cacert localhost.crt 'https://localhost/simple'
```

- with mTLS is needed certificates from server and client
```shell
curl --cacert localhost.crt --cert client.crt --key client.key 'https://localhost/secure'
```

### References

https://levelup.gitconnected.com/certificate-based-mutual-tls-authentication-with-nginx-57c7e693759d
