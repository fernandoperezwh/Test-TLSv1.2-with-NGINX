# Test TLS

## SMTP
### TLS Server
Construir la imagen del tls-smtp-server
```bash
sudo docker build -t tls-smtp-server .
```



Crear un contenedor con la imagen
```bash
sudo docker run --name tls-smtp-server \
	-p 25:25 \
	-p 143:143 \
	-p 993:993 \
	-d tls-smtp-server
```


```
swaks --to user@example.com --from sender@example.com --server localhost --port 25

swaks --to user@example.com --from sender@example.com --server localhost --port 25 --tls --tls-protocol tlsv1.2

```

## Nginx

### TLS Server
Construir la imagen del tls-server
```bash
sudo docker build -t tls-server .
```



Crear un contenedor con la imagen
```bash
sudo docker run --name tls-server \
	-p 80:80 \
	-p 443:443 \
	-d tls-server
```


### TLS Client
Construir la imagen del tls-client
```bash
sudo docker build -t tls-client .
```



Crear un contenedor con la imagen
```bash
sudo docker run --name tls-client \
	-d tls-client
```
