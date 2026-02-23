# 🌐 T02: Missió Apache: Desplegament Multidomini i Segur 🚀🔐

## Breu descripció

Les prediccions dels assessors de la incubadora s’han confirmat i ja teniu el vostre primer client real. **Projecte Nexus**, una nova empresa de formació situada a Mataró, us ha contractat per al desplegament i la gestió de la seva infraestructura web corporativa.

En aquesta fase inicial, l’objectiu és establir una base sòlida, segura i optimitzada per als seus serveis web abans de fer el desplegament definitiu al núvol ☁️. Nexus necessita allotjar diferents serveis web en un únic servidor, optimitzant recursos i garantint al mateix temps la màxima seguretat i rendiment.

Els requisits del client són clars:

- 🌍 Allotjar dos portals web diferenciats en un únic servidor:
  - `projectenexus.test` → Portal corporatiu  
  - `academia.test` → Portal de l’acadèmia de formació  
- 🔐 Garantir la seguretat de les comunicacions mitjançant xifratge SSL/TLS  
- ⚡ Assegurar un rendiment òptim utilitzant protocols moderns com HTTP/2  

Com a tècnics especialistes, la vostra missió és instal·lar, configurar i securitzar un servidor web **Apache sobre Ubuntu Server**, aplicant bones pràctiques professionals i documentant tot el procés.

---

## Descripció de l’encàrrec 🛠️

Abans del desplegament final en un servidor VPS a Internet, el projecte es desenvoluparà en una màquina virtual local per realitzar totes les proves necessàries. Un cop verificat el correcte funcionament i amb l’aprovació del client, el sistema es podrà desplegar en l’entorn de producció.

Les accions principals consisteixen en la instal·lació, configuració de dominis virtuals i securització avançada del servidor Apache.

---

## Tasques a realitzar 📋

### 1. Instal·lació i configuració base ⚙️

- Instal·lació del servidor web Apache a Ubuntu Server.  
- Verificació del funcionament del servei utilitzant la comanda `apachectl`.  
- Comprovació de la creació de l’usuari `www-data`.  
- Verificació dels permisos de la carpeta `/var/www`, que conté els fitxers web.

---

### 2. Desplegament de VirtualHosts (Multidomini) 🌐

Per optimitzar recursos, el servidor ha de poder allotjar diversos dominis simultàniament.

- Creació de l’estructura de directoris a `/var/www/` per separar els dos llocs web.  
- Configuració de dos VirtualHosts:
  - `projectenexus.test`
  - `academia.test`
- Utilització dels fitxers de configuració situats a `/etc/apache2/sites-available/`.  
- Activació dels llocs amb la comanda `a2ensite`.  
- Configuració de l’arxiu `hosts` per simular la resolució DNS i permetre l’accés als dominis.

---

### 3. Personalització de pàgines d’error 🎨

Configuració d’una pàgina d’error personalitzada per al codi **404 (Not Found)**, amb un missatge corporatiu i professional, evitant mostrar la pàgina d’error per defecte del servidor.

---

### 4. Seguretat i certificats SSL/TLS 🔐

Per garantir comunicacions segures:

- Habilitació del mòdul SSL a Apache.  
- Generació d’un certificat autosignat utilitzant OpenSSL amb les següents característiques:
  - Validesa de 365 dies  
  - Clau RSA de 2048 bits  
- Configuració dels VirtualHosts segurs utilitzant el port 443.  
- Configuració de la redirecció automàtica de HTTP (port 80) a HTTPS (port 443).

Això assegura que totes les comunicacions estiguin xifrades i protegides.

---

### 5. Optimització amb HTTP/2 ⚡

Per millorar el rendiment i la velocitat de càrrega:

- Activació del protocol HTTP/2 al servidor Apache.  
- Configuració de la directiva `Protocols` als VirtualHosts segurs.  
- Verificació del funcionament mitjançant eines com `curl` o el navegador web.

Aquest protocol permet una càrrega més ràpida i eficient dels recursos web.

---

## Què cal lliurar 📦

Cal redactar una **memòria tècnica completa** documentant tot el procés d’instal·lació i configuració del servidor Apache.

La memòria ha d’incloure:

- Explicacions clares de les configuracions realitzades 📝  
- Evidències del funcionament correcte ✔️  
- Verificació dels dominis configurats 🌐  
- Verificació de la seguretat HTTPS 🔐  
- Verificació del protocol HTTP/2 ⚡  

L’objectiu és que el client pugui entendre el desplegament realitzat, encara que no sigui un expert tècnic.

---

## Material de suport 📚

- UD5.AA2. El servidor Apache  
- Disponible al Moodle del mòdul de Serveis de Xarxa