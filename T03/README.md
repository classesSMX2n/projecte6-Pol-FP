# T03: Missió Nginx: Migració d'Alt Rendiment i Arquitectura Lleugera ⚡

## Breu descripció

Després de l'èxit de la implementació amb **Apache**, el client
**Projecte Nexus** ha mostrat satisfacció amb la infraestructura
desplegada. Tot i això, durant una reunió estratègica recent, la
direcció ha plantejat una nova preocupació: **l'escalabilitat del
sistema** davant possibles pics de trànsit.

Es preveu que durant la propera campanya de presentació de l'empresa el
portal rebi **un volum molt elevat de visites simultànies**. Per aquest
motiu, s'ha decidit iniciar una línia interna de **recerca i
desenvolupament (R+D)** per analitzar alternatives més eficients en
termes de rendiment.

Una de les opcions proposades és **Nginx**, un servidor web conegut per
la seva **arquitectura orientada a esdeveniments**, capaç de gestionar
milers de connexions concurrents amb un consum de memòria molt inferior
al d'altres servidors tradicionals.

L'objectiu d'aquesta activitat és **replicar la infraestructura creada
amb Apache**, però utilitzant **Nginx**, per tal de comparar el
comportament dels dos servidors i disposar d'una alternativa d'**alt
rendiment** dins del nostre catàleg de serveis.

⚠️ **Nota important:**\
Dos serveis no poden escoltar simultàniament els mateixos ports (**80 i
443**) a la mateixa IP. Per tant, caldrà **aturar el servei Apache abans
de començar la configuració amb Nginx**.

------------------------------------------------------------------------

## Descripció de l'activitat

### 1️⃣ Preparació de l'entorn i instal·lació 🖥️

**Objectiu:** Preparar el servidor per poder executar Nginx sense
conflictes amb altres serveis.

**Accions a realitzar:**

-   Aturar i deshabilitar el servei **Apache2** per alliberar els ports
    80 i 443.
-   Instal·lar el servidor web **Nginx** a Ubuntu Server.
-   Verificar que el servei està en funcionament i que la **pàgina de
    benvinguda de Nginx** es mostra correctament al navegador.

------------------------------------------------------------------------

### 2️⃣ Configuració de Server Blocks (Multidomini) 🌐

**Objectiu:** Configurar diversos dominis dins del mateix servidor
utilitzant Nginx.

**Accions a realitzar:**

-   Utilitzar l'estructura de carpetes ja creada.
-   Ajustar els permisos si és necessari perquè el propietari sigui **www-data**.
-   Configurar **dos Server Blocks** dins del directori: /etc/nginx/sites-available/
-   Activar-los creant **enllaços simbòlics** dins sites-enabled/.
-   Verificar la sintaxi amb nginx -t abans de reiniciar el servei.

------------------------------------------------------------------------

### 3️⃣ Personalització d'errors ❌

**Objectiu:** Mostrar una pàgina d'error corporativa quan es produeixi
un error.

**Accions a realitzar:**

-   Configurar la directiva **error_page 404** dins del bloc de servidor corresponent.
-   Assegurar que quan es demani un fitxer inexistent es mostri la **pàgina d'error personalitzada**.

------------------------------------------------------------------------

### 4️⃣ Seguretat i Certificats (HTTPS) 🔐

**Objectiu:** Garantir que totes les comunicacions amb el servidor
siguin segures.

**Accions a realitzar:**

-   Reutilitzar els **certificats SSL** generats a l'activitat anterior o generar-ne de nous.
-   Configurar el Server Block perquè escolti al **port 443**.
-   Configurar una **redirecció permanent (301)** des del port **80 (HTTP)** cap a **HTTPS**.

------------------------------------------------------------------------

### 5️⃣ Optimització amb HTTP/2 🚀

**Objectiu:** Millorar la velocitat de càrrega i el rendiment del
servidor.

**Accions a realitzar:**

-   Habilitar el protocol **HTTP/2** afegint el paràmetre `http2` a la directiva `listen`.
-   Verificar amb les eines de desenvolupador del navegador que el contingut s'està servint amb aquest protocol.

------------------------------------------------------------------------

## Què cal lliurar 📄

Redactar una **memòria tècnica completa** amb:

-   Explicacions clares de cada pas realitzat.
-   Captures de pantalla del procés d'instal·lació i configuració.
-   Proves de funcionament que demostrin:
    -   Funcionament dels dominis configurats
    -   HTTPS actiu
    -   HTTP/2 funcionant

⚠️ La memòria ha d'incloure **explicacions**, no només captures de pantalla.

------------------------------------------------------------------------

## Material de suport 📚

-   **UD5.AA2. El servidor Nginx**\
    Disponible al Moodle del mòdul de **Serveis de Xarxa**.
