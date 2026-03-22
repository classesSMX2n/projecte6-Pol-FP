# Windows Server

## 0. Replantejament d'OUs

Volem endurir la política de contrasenyes de l'empresa, però abans de començar ens haurem de replantejar l'estructura actual d'**Organizational Units (OU)**.

---

## 1. Polítiques de seguretat i contrasenyes (Seguretat corporativa)

Per començar obrirem **Group Policy Management Editor** i anirem a la *Password Policy* dels ordinadors.

![](img/01.png)

Primer farem doble clic a **Relax minimum password length limits** i habilitarem la política.

![](img/02.png)

A continuació establirem el mínim fent clic a **Minimum password length** i canviant el valor.

![](img/03.png)

Com podem veure, si posem una contrasenya de **7 caràcters**, el sistema no ens deixarà continuar.

![](img/03.1.png)  
![](img/03.2.png)

A **Group Policy Management** farem clic dret i seleccionarem **Create a GPO in this domain**.

![](img/04.png)

Li posem un nom i editem la política de contrasenya de la **GPO de Gerència**.

![](img/05.png)  
![](img/06.png)

Movem el grup i els usuaris a la plantilla dels usuaris de gestió dins de la **OU** perquè s'apliqui la GPO.

![](img/07.png)

Com podem veure, si posem **17 caràcters**, tampoc ens deixarà canviar la contrasenya. Això confirma que **la GPO de Gerència s'ha aplicat per sobre de la GPO per defecte**.

![](img/07.1.png)  
![](img/07.2.png)

**GPO EXTRA**

---

# 2. Instal·lació desatesa de programes

Per començar crearem una **nova carpeta compartida**, la qual haurem de configurar perquè **tothom dins del domini la pugui llegir** i **els administradors puguin llegir i escriure**.

![](img/08.png)

Dins de la carpeta hi col·locarem l'arxiu **.msi de 7zip**.

![](img/09.png)

Dins la **OU Usuaris** crearem una GPO que es digui **7zip_gestio**.

![](img/10.png)

Anirem fins a **Software Installation**.

![](img/11.png)

Una vegada aquí farem clic dret i crearem un **nou package**.

![](img/12.png)

Haurem d'indicar la ruta del paquet **utilitzant la ruta de xarxa**.

![](img/13.png)

Ara seleccionarem **Advanced** per poder veure tota la configuració.

![](img/14.png)

A continuació anirem a **Deployment**, seleccionarem **Assigned** i activarem **Install this application at logon**.

![](img/15.png)

## Aplicar una GPO a un grup específic

Ara anirem a la **GPO que hem creat** i, a **Security Filtering**, eliminarem **Authenticated Users**.

![](img/16.png)

Després anirem a **Delegation**, farem clic a **Add** i afegirem **Authenticated Users** amb permisos només de **Read**.

![](img/17.png)  
![](img/18.png)

Una vegada fet això, anirem a **Scope**, farem clic a **Add** i seleccionarem el grup al qual volem aplicar la GPO.

![](img/19.png)

Ara, si iniciem sessió amb un **usuari de gestió**, **7zip s'instal·larà automàticament**.

![](img/20.png)

Ara crearem una nova **GPO a la OU Gerència** perquè, si els usuaris de gerència volen instal·lar **Firefox**, ho puguin fer.

Repetirem el mateix procés, però a les propietats seleccionarem **Published** en lloc de **Assigned**.

![](img/21.png)

Farem que la GPO només s'apliqui al **grup Gerència**.

![](img/22.png)

Ara, si entrem amb un usuari de gerència, podrem anar al **Panell de control → Programes i característiques** i veure l'opció **Instal·lar programes des de la xarxa**.

![](img/23.png)  
![](img/24.png)

---

# 3. Conversió de .exe a .msi

*(Secció pendent d'afegir contingut.)*

---

# 4. Perfils mòbils

Els usuaris de gestió normalment canvien entre **portàtil i equip d'escriptori**. Com a solució utilitzarem **perfils mòbils**.

Començarem creant una **nova carpeta compartida anomenada `perfils`** i li assignarem **els mateixos permisos que la carpeta homes**.

![](img/25.png)

Ara editarem les propietats de la plantilla. Anirem a **Profile** i canviarem la ruta del perfil per la carpeta creada.

És important afegir **%USERNAME% al final**.

![](img/26.png)

Crearem un nou usuari amb la plantilla editada i iniciarem sessió.

Com a resultat, es crearà automàticament una carpeta dins de **perfils**.

![](img/27.png)  
![](img/28.png)

---

# 5. Redirecció de carpetes

Tornem al **Default Domain Policy**.

![](img/29.png)

Anirem a **Folder Redirection**.

![](img/30.png)

Configurarem la redirecció cap a la nostra **carpeta homes**.

![](img/31.png)

Ara, quan iniciem sessió, veurem que la carpeta **Documents** apareix com **En línia**, cosa que indica que està sincronitzada.

![](img/32.png)

També podem veure que l'arxiu es troba dins la carpeta del servidor.

![](img/32.1.png)

---

# 6. Delegació

L'objectiu és **delegar funcions a altres usuaris**, per exemple un **administrador d'usuaris** que pugui gestionar altres comptes.

Començarem entrant a la **màquina client com a administrador**.

Anirem a **Configuració → Característiques opcionals**.

![](img/33.png)

Seleccionarem **Veure característiques**, buscarem **RSAT** i instal·larem les dues opcions que es mostren a la imatge.

![](img/34.png)  
![](img/35.png)

Esperarem fins que finalitzi la instal·lació.

![](img/36.png)

Des de la màquina client, si iniciem sessió com a **Administrador**, podrem utilitzar les eines de gestió.

![](img/37.png)

Ara seleccionarem **Agregar otros servidores para administrar**.

![](img/38.png)

Introduirem el **nom del nostre servidor** i l'afegirem.

![](img/39.png)

Com podem veure, el servidor s'ha afegit correctament.

![](img/40.png)

Ara crearem un nou usuari anomenat **adminOU** dins de la **OU Usuaris**.

![](img/41.png)

Farem clic dret sobre la **OU Usuaris** i seleccionarem **Delegate Control**.

![](img/42.png)

Seleccionarem **Add** i introduirem el nom de l'usuari **adminOU**, que serà a qui delegarem les funcions.

![](img/43.png)

Delegarem les funcions de:

- Restablir contrasenyes
- Modificar la pertinença d'usuaris als grups

![](img/44.png)

Iniciem sessió amb **adminOU**.

![](img/45.png)

Anirem a **Herramientas → Usuarios y equipos de Active Directory**.

![](img/46.png)

Seleccionarem un usuari i **restablirem la seva contrasenya**.

![](img/47.png)  
![](img/48.png)  
![](img/49.png)

També podrem **afegir l'usuari a grups**.

![](img/51.png)  
![](img/52.png)

Si intentem fer una altra acció que **no hem delegat**, com per exemple **eliminar un usuari**, veurem que **no tenim permisos**.

![](img/53.png)