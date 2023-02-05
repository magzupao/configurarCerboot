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

comandos utiles nginx
```
sudo systemctl stop nginx
sudo systemctl start nginx
sudo systemctl restart nginx
sudo systemctl reload nginx
sudo systemctl disable nginx
sudo systemctl enable nginx

```

configuramos servidor
```
sudo mkdir -p /var/www/your_domain/html

nano /var/www/your_domain/html/index.html

```
contenido index.html

```
<html>
    <head>
        <title>Welcome to your_domain</title>
    </head>
    <body>
        <h1>Success! Your Nginx server is successfully configured for <em>your_domain</em>. </h1>
<p>This is a sample page.</p>
    </body>
</html>
```

creamos un dominio
```
sudo nano /etc/nginx/sites-available/your_domain
```

contenido del dominio:
```
server {
        listen 80;
        listen [::]:80;

        root /var/www/your_domain/html;
        index index.html index.htm index.nginx-debian.html;

        server_name your_domain www.your_domain;

        location / {
                try_files $uri $uri/ =404;
        }
}
```

creamos link
```
sudo ln -s /etc/nginx/sites-available/your_domain /etc/nginx/sites-enabled/
```

habilitamos memoria
```
sudo nano /etc/nginx/nginx.conf

...
http {
    ...
    server_names_hash_bucket_size 64;
    ...
}
...

```
