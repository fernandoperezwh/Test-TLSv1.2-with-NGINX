# Test TLS

## TLS Server
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


## TLS Client
Construir la imagen del tls-client
```bash
sudo docker build -t tls-client .
```



Crear un contenedor con la imagen
```bash
sudo docker run --name tls-client \
	-d tls-client
```
