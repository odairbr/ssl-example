# ssl-example
SSL certificate study

## Generate certificate

```shell
openssl req -x509 \
            -sha256 -days 356 \
            -nodes \
            -newkey rsa:2048 \
            -subj "/CN=localhost.spec/C=BR/L=São Paulo" \
            -keyout rootCA.key -out rootCA.crt
```
