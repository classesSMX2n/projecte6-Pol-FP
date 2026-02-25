# Apache

## 1. Instal·lació i configuració base 

Propietats de la maquina virtual:
![](img/01.png)

abanç de fer qualsevol cosa actualitzarem la maquina amb:
```bash
sudo apt update && sudo apt upgrade -y
```

Ara instalarem apache2 amb:
```bash
sudo apt install apache2
```

Per comprobar que apache esta funcionant de manera correcta
```bash
systemctl status apache2
```
![](img/02.png)

Comprovem que el usuari i grup www-data s'han creat amb
```bash
grep www-data /etc/passwd
```
![](img/03.png)

Revisem que la carpeta /var/www tingui permisos de lectura per tots el usuaris excepte root
```bash
ls -l /var
```
![](img/04.png)

## 2. Desplegament de VirtualHosts

Per començar editarem el arxiu /etc/hosts pero els 2 dominis
```bash
sudo nano /etc/hosts
```
![](img/05.png)

A continuació crearem els directoris necessaris a /var/www per allotjar els 2 llocs per separat de manera organitzada
```bash
sudo mkdir /var/www/projectenexus
sudo mkdir /var/www/academia
```

També haurem de crear un index.html a dins de cada carpeta 
```bash
sudo nano /var/www/projectenexus/index.html
sudo nano /var/www/academia/index.html
```
![](img/06.png)
![](img/07.png)

Configurarem 2 VirtualHosts a /etc/apache2/sites-available/ copiarem el arxiu de configuració per defecte aixins 
```bash
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/projectenexus.conf
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/academia.conf
```

Editarem els arxius de config amb 
```bash
sudo nano /etc/apache2/sites-available/projectenexus.conf
sudo nano /etc/apache2/sites-available/academia.conf
```
![](img/08.png)
![](img/09.png)

Ara cargarem els sites que em creat amb
```bash
sudo a2ensite projectenexus.conf
sudo a2ensute academia.conf
```
haurem de tornar a carregar el servei per que les pagines carreguin
```bash
sudo systemctl reload apache2
```
![](img/10.png)

Pagina de Projectenexus
![](img/11.png)

Pagina de Academia
![](img/12.png)

## 3. Personalització d'Errors

Per poder posar una pagina d'error 404 personalitzada haurem de crear un 404.html 
```bash
sudo nano /var/www/projectenexus/404.html
sudo nano /var/www/academia/404.html
```
![](img/13.png)
![](img/14.png)

Per que en cas de error 404 la nostra web carregui el arxiu que acabem de crear haurem de cambiar la configuracio del nostra site
```bash
sudo nano /etc/apache2/sites-available/projectenexus.conf
sudo nano /etc/apache2/sites-available/academia.conf
```
![](img/15.png)
![](img/16.png)

Error 404 projectenexus:
![](img/17.png)

Error 404 academia:
![](img/18.png)

## 4. Seguretat i Certificats (HTTPS)

Per poder habilitar diferents llocs amb pagina segura (SSL) copiarem l'arxiu per defecte TLS 
```bash
sudo cp /etc/apache2/sites-available/default-ssl.conf /etc/apache2/sites-available/projectenexus-ssl.conf
sudo cp /etc/apache2/sites-available/default-ssl.conf /etc/apache2/sites-available/academia-ssl.conf
```

Ara crearem les carpetes on guardarem les claus del certificat autosignat que utilitzarem
```bash
sudo mkdir /var/www/projectenexus/cert && sudo mkdir /var/www/projectenexus/private
sudo mkdir /var/www/academia/cert && sudo mkdir /var/www/academia/private
```

Per crear un Certificat autosignat per els dominis projectenexus.test i academia.test utilitzarem OpenSSL el certificat haura de tenir una duració de 365 dies i una clau RSA de 2048 bits. **NOMES ES MOSTRARA LA CREACIÓ DE LA CLAU PER PROJECTE NEXUS CAL REPETIR EL PROCESS PER ACADEMIA**
```bash
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /var/www/projectenexus/private/projectenexus.key -out /var/www/projectenexus/cert/projectenexus.crt
```
![](img/19.png)

A continuació haurem de editar el arxiu projectenexus-ssl.conf
```bash
sudo nano /etc/apache2/sites-available/projectenexus-ssl.conf
```
![](img/20.png)

Per habilitar el protocol https en apache2 cal fer
```bash
sudo a2enmod ssl
sudo a2ensite projectenexus-ssl.conf
systemctl restart apache2
```

Ara configurarem el servidor perque qualsevol peticio HTTP es redirigeixi automaticament a HTTPS
```bash
sudo nano /etc/apache2/sites-available/projectenexus.conf
```
![](img/21.png)

Recargarem la configuració de apache2 amb
```bash
sudo systemctl reload apache2
```

Com podrem veure a partir d'ara quan posem www.projectenexus.test ens anira per conexio segura mitjançant HTTPS
![](img/22.png)
![](img/23.png)

Ara ensenyare el resultat d'Academia
![](img/24.png)
![](img/25.png)

Ara neceistem bloquejar la carpeta private per que no es convenient que qualsevol persona pugui accedir a dins i d'aquesta manera accedir a la clau privada per fer aixo editarem l'arxiu projectenexus-ssl.conf
```bash
sudo nano /etc/apache2/sites-available/projectenexus-ssl.conf
```
![](img/26.png)

Recargarem la configuració de apache2 amb
```bash
sudo systemctl reload apache2
```

Com podem veure no podem accedir a el directory private a projectenexus.test
![](img/27.png)

Ara mostrare com no es pot accedir a academia tampoc
![](img/28.png)

## 5. 