# Protecció de dades

## Tasca 1

Obrirem el nostre programa veracrypt i li donarem a crear volumen
![](img/01.png)

Ara Li donarem a cifrar partición/unidad secundaria
![](img/02.png)

Clickarem a volumen veracrypt comun
![](img/03.png)

Li donarem a seleccionar Dispositivo i seleccionarem el dispositiu/volum que volguem cifrar
![](img/04.png)

Seleccionarem la opcio de xifrar i conservar les nostres dades
![](img/05.png)

Cambiarem els menus desplegables marcats en el primer posarem l'opcio AES i a la segona posarem SHA-256
![](img/06.png)

Posarem una contrasenya robusta
![](img/07.png)

Aqui el programa ens dira de moure dins de la finestra el ratoli per augmentar la aleatoritat de la criptografia
![](img/08.png)

Aqui deixarem la configuracio per defecte que es ninguno i continuarem
![](img/09.png)

Deixarem aquesta configuració per defecte i donarem cifrar
![](img/10.png)

Veurem la pestaña de volumen xifrat i li donarem a finalitzar
![](img/11.png)

Ens anirem al programa de Veracrypt li donarem a seleccionar dispositivo i seleccionarem el nostre pendrive/volumen xifrat
![](img/12.png)

Una vegada fet aixo seleccionarem una lletra i li donarem a montar
![](img/13.png)

Posarem la contrasenya i li donarem a aceptar
![](img/14.png)

Una vegada fet aixo ara podrem accedir al nostre pendrive xifrat
![](img/15.png)

Posarem un arxiu en aquest cas es diu EXAMEN_FINAL_SEGURETAT i a dins tindrem unes preguntes
![](img/16.png)

A continuació desmontarem la unitat 
![](img/17.png)

Si no montem el pendrive amb la contrasenya no podrem accedir a les dades a dins
![](img/18.png)

## Tasca 2

Per comprobar la integritat d'un arxiu podem utilitzar una eina com CertUtil,
Per començar crearem un arxiu anomenat nota_final_curs.txt i posarem a dins L'alumne ha aprovat amb un 5
![](img/19.png)

Obrirem un powershell escribint a dalt de la carpeta on es el nostre arxiu nota_final_curs.txt
![](img/20.png)

ara escriurem la seguent comanda per calcular el hash SHA-256 que com podem veure ens dona el hash
![](img/21.png)

Ara cambiarem la nota del alumne per un 9 i guardarem l'arxiu
![](img/22.png)

Ara calcularem el hash una altre vegada el que demostra que canvia totalment el que demostra la manipulació del arxiu
![](img/23.png)

Com podem observar els 2 hash son diferents elque significa que l'arxiu ha sigut editat
![](img/24.png)
![](img/25.png)

## Diferència entre xifratge i hash

El xifratge serveix per amagar la informació perquè ningú hi pugui accedir sense la contrasenya. Quan xifrem una unitat d’emmagatzematge (com un disc o un pendrive), els arxius que hi ha dins queden protegits i no es poden llegir ni modificar si no es munta amb la clau correcta. Això garanteix la confidencialitat de les dades, especialment si el dispositiu es perd o és robat.

En canvi, la funció hash no amaga la informació. El que fa és agafar tot el contingut d’un fitxer (per exemple, el text d’un PDF o d’un document) i generar un codi únic, com una empremta digital. Aquest codi és un número molt llarg. Si es canvia qualsevol cosa del fitxer, encara que sigui només una lletra o un número, el hash canvia completament. Això permet comprovar si el fitxer ha estat modificat.

Per tant, el xifratge protegeix la informació perquè no es pugui llegir, mentre que el hash serveix per assegurar que el contingut no ha estat alterat.