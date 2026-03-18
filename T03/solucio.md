#  NGINX

## 0. Previ

Maquina client
![](img/01.png)

Maquina Virtual
![](img/02.png)

Ip Server
![](img/03.png)

Ip client
![](img/04.png)

Prova de conectivitat
![](img/05.png)

## 1.Instal·lació i Base

Per començar pararem i desahbilitarem apache2 per que el servei fa conflicte amb nginx
```bash
sudo systemctl stop apache2
sudo systemctl disable apache2
```

Instal·lem Ngnix 
```bash
sudo apt install nginx -y
```

Comprovem l'estat de nginx amb:
```bash
sudo systemctl status nginx
```
![](img/06.png)

## 2. Server Blocks

A continuació copiarem el arxiu default del server
```bash
sudo cp /etc/ngnix/sites-available/default /etc/nginx/sites-available/projectenexus
sudo cp /etc/ngnix/sites-available/default /etc/nginx/sites-available/academia
```

Editarem els arxius default que acabem de crear
```bash
sudo nano /etc/nginx/sites-available/projectenexus
sudo nano /etc/nginx/sites-available/academia
```
![](img/07.png)
![](img/08.png)

Ara haurem de crear un enllaç simbolic
```bash
sudo ln -s /etc/nginx/sites-available/projectenexus /etc/nginx/sites-enabled/
sudo ln -s /etc/nginx/sites-available/academia /etc/nginx/sites-enabled/
```

Com treballarem amb diferents noms editarem l'arxiu /etc/nginx/nginx.conf esborrarem el #
```bash
sudo nano /etc/nginx/nginx.conf
```
![](img/09.png)

Per comprovar que no hi han errors sintactics a la configuració 
```bash
sudo nginx -t
```
![](img/10.png)

Reiniciarem el servei
```bash
sudo systemctl restart nginx
```

Pagina web projectenexus:
![](img/11.png)

Pagina web academia:
![](img/12.png)

## 3. Pagina d'error 404

