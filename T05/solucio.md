# Protecció de dades – Projecte Nexus

## Introducció

Projecte Nexus gestiona una gran quantitat de dades sensibles, com dades personals d’estudiants, exàmens oficials no publicats i certificats de notes. Per aquest motiu, és fonamental garantir els tres pilars de la seguretat de la informació: confidencialitat, integritat i autenticitat.

En aquest informe es presenta una demostració pràctica de com protegir les dades en repòs mitjançant xifratge i com verificar la integritat dels fitxers utilitzant funcions hash.

---

# Tasca 1 – Protecció de dades en repòs (Xifratge amb VeraCrypt)

Obrirem el programa **VeraCrypt** i farem clic a **Crear volum**.  
![](img/01.png)

Seleccionarem l’opció **Xifrar partició/unitat secundària**.  
![](img/02.png)

Escollirem l’opció **Volum VeraCrypt estàndard**.  
![](img/03.png)

Farem clic a **Seleccionar dispositiu** i triarem el dispositiu o volum que volem xifrar (pendrive simulat).  
![](img/04.png)

Seleccionarem l’opció **Xifrar la partició conservant les dades existents**.  
![](img/05.png)

Configurarem els següents paràmetres:

- Algorisme de xifratge: AES  
- Algorisme hash: SHA-256  

![](img/06.png)

Introduirem una **contrasenya robusta**, combinant majúscules, minúscules, números i símbols.  
![](img/07.png)

Mourem el ratolí dins la finestra per augmentar l’aleatorietat del xifratge i millorar la seguretat.  
![](img/08.png)

Deixarem la configuració per defecte i continuarem.  
![](img/09.png)

Farem clic a **Xifrar** per iniciar el procés.  
![](img/10.png)

Un cop finalitzat el procés, farem clic a **Finalitzar**.  
![](img/11.png)

Per accedir al volum xifrat, tornarem a la finestra principal de VeraCrypt, farem clic a **Seleccionar dispositiu** i escollirem el volum xifrat.  
![](img/12.png)

Assignarem una lletra d’unitat i farem clic a **Muntar**.  
![](img/13.png)

Introduirem la contrasenya i farem clic a **Acceptar**.  
![](img/14.png)

Ara podem accedir al volum xifrat com si fos una unitat normal.  
![](img/15.png)

Dins del volum xifrat, crearem el fitxer: **EXAMEN_FINAL_SEGURETAT.txt**. Aquest fitxer conté preguntes de prova.  
![](img/16.png)

Després desmuntarem la unitat.  
![](img/17.png)

Si intentem accedir al dispositiu sense muntar-lo amb la contrasenya, no podrem llegir el contingut, demostrant que les dades estan protegides.  
![](img/18.png)

---

# Tasca 2 – Verificació d’Integritat (Hashing)

Crearem un fitxer anomenat **nota_final_curs.txt** a dins escriurem "L'alumne ha aprovat amb un 5"
![](img/19.png)

Obrirem una finestra de **PowerShell** des de la carpeta on es troba el fitxer.  
![](img/20.png)

Executarem la següent comanda per calcular el hash SHA-256: CertUtil -hashfile nota_final_curs.txt SHA256
![](img/21.png)

Ara modificarem el contingut del fitxer canviant la nota a 9 i guardarem l'arxiu
![](img/22.png)

Ara calcularem el hash una altre vegada el que demostra que canvia totalment el que demostra la manipulació del arxiu
![](img/23.png)

Podem observar que el hash ha canviat completament. 
![](img/24.png)
![](img/25.png)

Això demostra que qualsevol modificació del fitxer, encara que sigui mínima, canvia totalment el hash i permet detectar manipulacions.

## Diferència entre xifratge i hash

El xifratge serveix per amagar la informació perquè ningú hi pugui accedir sense la contrasenya. Quan xifrem una unitat d’emmagatzematge (com un disc o un pendrive), els arxius que hi ha dins queden protegits i no es poden llegir ni modificar si no es munta amb la clau correcta. Això garanteix la confidencialitat de les dades, especialment si el dispositiu es perd o és robat.

En canvi, la funció hash no amaga la informació. El que fa és agafar tot el contingut d’un fitxer (per exemple, el text d’un PDF o d’un document) i generar un codi únic, com una empremta digital. Aquest codi és un número molt llarg. Si es canvia qualsevol cosa del fitxer, encara que sigui només una lletra o un número, el hash canvia completament. Això permet comprovar si el fitxer ha estat modificat.

Per tant, el xifratge protegeix la informació perquè no es pugui llegir, mentre que el hash serveix per assegurar que el contingut no ha estat alterat.