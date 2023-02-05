# configurarCerboot
configuramos certificados digitales

tomamos de referencia la pagina:
https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-debian-10

Ejecutamos las siguientes acciones:
```
sudo apt update

sudo apt install python3-acme python3-certbot python3-mock python3-openssl python3-pkg-resources python3-pyparsing python3-zope.interface

sudo apt install python3-certbot-nginx

```

configuramos el servidor nginx
https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-debian-10#step-5-%E2%80%93-setting-up-server-blocks

Instalamos nginx
```
sudo apt update

sudo apt install nginx

systemctl status nginx

http://your_server_ip

```
