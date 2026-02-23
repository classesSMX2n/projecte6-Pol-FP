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

![]()