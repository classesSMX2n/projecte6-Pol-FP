# Windows Server 

## 0. Repensament d'Ou's

Volem endurir la politica de contrasenyes de la empresa pero per poder començar ens haurem de repensar l'actual Estructura d'OUs

## 1. Polítiques de Seguretat i Contrasenyes (Seguretat Corporativa).

Per comencar obrirem el Group Policy Managment Editor i anirem a la password policy dels ordinadors
![](img/01.png)

Primer farem doble click a Relax minimum password length limits i habilitem la politica
![](img/02.png)

A continuació establim el minim donant click a Minimum password length i cambiant el valor
![](img/03.png)

Com podem veure si posem una contrasenya de 7 caracters no ens deixara
![](img/03.1.png)
![](img/03.2.png)

A group Policy managment farem click dret i li donarem a Create a GPO in this domain
![](img/04.png)

Li posem un nom i editarem la politica de contrasenya de la GPO per Gerencia
![](img/05.png)
![](img/06.png)

Movem el grup i els usuauris a la plantilla dels usuaris de gestio a dins de la OU per que s'apliqui la GPO 
![](img/07.png)

**GPO EXTRA**

---

## 2. Instal·lacio desatesa de programes

Per començar crearem una nova carpeta compartida la cual haurem de fer que tothom dins del domini la pugui lleguir i els admins lleguir i escriure 
![](img/08.png)

A dins de la carpeta ficarem el arxiu .msi de 7zip
![](img/09.png)

Dins la OU Usuaris crearem una GPO que es digui 7zip_gestio
![](img/10.png)

Anirem fins a Software Installation
![](img/11.png)

Una vegada aqui farem click dret i crearem un nou package 
![](img/12.png)

Haurem d'indicar la ruta del paquet **amb la ruta de xarxa**
![](img/13.png)

Ara li donarem a advanced per poder veure tota la configuració del
![](img/14.png)

Ara anirem a Deployment donarem a la opcio Assigned i li donarem a Install this application at logon li donem a ok
![](img/15.png)

**ELS SEGUENTS PASSOS SON PER APLICAR UNA GPO A UN GRUP ESCPECIFIC**

Ara anirem a la GPO que em creat i anem a security filtering i eliminem la unica que hem de tenir que es diu Authenticated Users
![](img/16.png)

Ara anireme a Delegation i donem a add i afegim Authenticated Users i li donem nomes permisos de llegir
![](img/17.png)
![](img/18.png)

una vegada fet aixo anem a Scope i li donem a add i posem el grup que volguem que afecti aquesta GPO
![](img/19.png)

Ara si iniciem sessio amb un usuari de gestio el 7zip sera instalat de manera automatica
![](img/20.png)

Ara haurem de crear una nova GPO a la nostra OU gerencia per que si els usuaris de gerencia es volen instalar firefox se'l puguin instalar repetirem tot el mateix proces menys a les propietats que en comptes de posar que siguin assignades posarem que siguin publicades
![](img/21.png)

Farem que la GPO només s'apliqui per el grup gerencia
![](img/22.png)

Ara si entrem amb un usuari de gerencia podrem entrar al panell de control i al apartat de programas i caracteristicas podrem veure una opcio que posa Instalar programas desde la red, com podem veure podem instalar firefox 
![](img/23.png)
![](img/24.png)

## 3. .exe a .msi


## 4. Perfils Mobils
Els usuaris de gestio normalment cambien entre portatil i equip d'escriptori com a solucio a aixo farem perfils mobils.

Començarem creant una nova carpeta compartida ques digui perfils i la compartirem posarem els mateixos permissos que els de la carpeta homes
![](img/25.png)

Ara editarem les propietats de la plantilla anirem a profile i cambiarem la ruta del perfil per la carpeta que em posat important posarem al final %USERNAME%
![](img/26.png)

Crearem un nou usuari amb la plantilla editada i intentarem iniciar sessio en ell com a resultat sen's creara una carpeta a dins de la carpeta perfils
![](img/27.png)
![](img/28.png)

## 5. Redireccio de carpetes

Tornem al Default Domain Policy
![](img/29.png)

Anirem a Folder Redirection
![](img/30.png)

Configurarem la redireccio cap a la nostra carpeta de homes
![](img/31.png)

Com podem veure ara que em iniciat sessio ens surt que la carpeta Documentos esta En línea aixo vol dir que esta sincronitzat
![](img/32.png)

## 6. Delegació

Aqui el que volem fer es delegar funcions a altres usuaris ex un administrador d'usuaris que gestioni els altres usuaris 
S
Començarem entrant a la nostra maquina client com a administrador anirem a la configuració i cercarem caracteristicas opcionales
![](img/33.png)

anirem a ver caracteristicas cercarem rsat i descarragarem les 2 que es veuen en pantalla
![](img/34.png)
![](img/35.png)

Esperarem fins que acabi la instalació
![](img/36.png)

Si desde la maquina client fem login com a Adminisitrador podrem utilitzar les eines de gestio
![](img/37.png)

Ara li donarem a agregar otros servidores para administrar
![](img/38.png)

Posarem el nom del nostre server i el afegirem
![](img/39.png)

Com podem veure s'ha afegit correctament el server
![](img/40.png)

Ara crearem un nou usuari que es digui adminOU el crearem a dins de la OU usuaris
![](img/41.png)

farem click dret a la OU de usuaris i li donarem a delegate control
![](img/42.png)

Li donem a add i escriurem el nom del usuari que em creat que sera al que delegarem les funcions 
![](img/43.png)

Delegarem les funcions de reiniciar contrasenyes i modificar la pertinença de altres usuaris al grup
![](img/44.png)

Iniciem sessio com adminOU
![](img/45.png)

Entramos a Herramientas y seleccionamos Usuarios y equipos de Active Directory
![](img/46.png)

Anirem a un usuari i restablirem la contrasenya 
![](img/47.png)
![](img/48.png)
![](img/49.png)

Com podem veure tambe afegir a grups el usuari 
![](img/51.png)
![](img/52.png)