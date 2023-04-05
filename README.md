# ssl-example
SSL certificate study

## Generate certificate

```shell
openssl req -x509 \
            -sha256 -days 365 \
            -nodes \
            -newkey rsa:2048 \
            -subj "/CN=localhost/C=BR/ST=São Paulo/L=São Paulo/O=Test SSL" \
            -keyout certificates/localhost.key -out certificates/localhost.crt
```
