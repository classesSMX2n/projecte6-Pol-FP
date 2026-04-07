# Projecte Nexus
## Informe tècnic de la proposta d’infraestructura E-learning

---

# 1. Context i necessitats del client

L'empresa **Nexus e-learning** és una organització dedicada a la formació tecnològica que vol ampliar la seva oferta educativa mitjançant la creació d'una plataforma de formació online pròpia.

L'objectiu principal del projecte és desplegar una infraestructura tecnològica capaç d'allotjar una plataforma d'aprenentatge virtual orientada a **cursos per a tècnics informàtics**. Aquesta plataforma ha de permetre la publicació de continguts educatius, la gestió d'usuaris i cursos, així com la interacció entre estudiants i professors.

Per aconseguir-ho, Nexus necessita una solució tècnica basada en una infraestructura de servidor estable i eficient, que permeti garantir el correcte funcionament de la plataforma en un entorn real.

Aquest projecte simula una situació habitual dins del món professional, en la qual una empresa necessita analitzar diferents tecnologies abans de prendre una decisió sobre quina infraestructura desplegar.

## Objectius del projecte

El projecte té diversos objectius principals:

- desplegar un servidor capaç d’allotjar una plataforma e-learning funcional
- analitzar i comparar diferents tecnologies de servidor web
- estudiar diferents plataformes LMS
- proposar una solució tècnica viable i sostenible
- justificar les decisions preses des d’un punt de vista tècnic

Aquests objectius permeten construir una proposta completa que respongui a les necessitats del client.

## Necessitats principals del client

Per tal que la plataforma sigui viable, la infraestructura ha de complir diversos requisits tècnics i operatius.

### Rendiment

La plataforma ha de ser capaç de suportar múltiples usuaris connectats simultàniament sense afectar negativament el temps de resposta del sistema. Això és especialment important en plataformes de formació online, on els usuaris poden accedir al mateix temps a continguts, activitats i materials educatius.

### Cost controlat

Com que el projecte està pensat per una petita o mitjana organització, és essencial que la solució proposada tingui **costos d'implantació i manteniment moderats**. La infraestructura ha de ser suficientment potent per suportar la plataforma, però sense generar despeses innecessàries.

### Sostenibilitat

Un dels criteris importants del projecte és la sostenibilitat tecnològica. Això implica utilitzar solucions que optimitzin el consum de recursos del servidor i redueixin el consum energètic. La selecció d’eines eficients contribueix a reduir l’impacte ambiental de la infraestructura.

### Facilitat de manteniment

Finalment, el sistema ha de ser fàcil d’administrar i mantenir. Això implica que les tecnologies seleccionades han de tenir bona documentació, una comunitat activa i eines que facilitin la gestió del sistema.

Aquest conjunt de necessitats serà el punt de partida per a les decisions tècniques que es presentaran en els apartats següents de l’informe.

---

# 2. T04 — Duel de titans: Apache vs Nginx

Per seleccionar el servidor web més adequat per al projecte Nexus, s'ha realitzat una comparativa entre **Apache** i **Nginx**, dues de les tecnologies més utilitzades en entorns web.

## 2.1 Comparativa tècnica

| Característica | Apache | Nginx |
|---|---|---|
| Instal·lació | Senzilla | Senzilla |
| Configuració | Molt flexible | Més estructurada |
| Rendiment | Bo | Molt alt |
| Consum de recursos | Mitjà | Baix |
| Escalabilitat | Bona | Molt bona |
| Manteniment | Relativament senzill | Senzill |

Apache és conegut per la seva flexibilitat i gran compatibilitat amb aplicacions web. Nginx, en canvi, destaca per la seva arquitectura orientada a esdeveniments, que permet gestionar moltes connexions amb menys recursos.

---

## 2.2 Experiència real durant el projecte

Durant el desplegament pràctic del projecte es van utilitzar tots dos servidors per observar-ne el comportament real.

### Experiència amb Apache

Aspectes positius:

- Gran quantitat de documentació disponible
- Sistema molt flexible de configuració
- Compatibilitat amb múltiples mòduls

Dificultats trobades:

- Consum de memòria relativament elevat
- Algunes configuracions poden resultar complexes en entorns amb múltiples serveis

---

### Experiència amb Nginx

Aspectes positius:

- Configuració clara i ordenada
- Millor gestió de múltiples connexions simultànies
- Consum de recursos més reduït

Dificultats trobades:

- Algunes configuracions requereixen més coneixement tècnic
- Menys flexibilitat en alguns aspectes comparat amb Apache

Aquesta experiència pràctica ha estat fonamental per entendre el funcionament real de cada servidor.

---

## 2.3 Mètriques i dades observades

Durant les proves pràctiques es van obtenir algunes dades orientatives:

- Temps aproximat d'instal·lació d’Apache: **10 minuts**
- Temps aproximat d'instal·lació de Nginx: **8 minuts**

Consum de recursos aproximat:

- **Apache:** consum de RAM més elevat
- **Nginx:** consum de RAM més reduït

També es va observar que **Nginx responia amb més rapidesa quan hi havia diverses connexions simultànies**.

---

## 2.4 Decisió final del servidor web

Després d’analitzar les dues tecnologies, la solució escollida és **Nginx**.

### Justificació de la decisió

La decisió es basa en diversos factors:

- millor rendiment general
- menor consum de recursos
- millor comportament en entorns VPS
- major eficiència energètica

Aquests factors encaixen millor amb les necessitats del projecte Nexus, especialment en relació amb la **sostenibilitat i l'eficiència del sistema**.

---

# 3. T11 — Comparativa Moodle vs Canvas LMS

Per seleccionar la plataforma d'aprenentatge virtual (LMS) més adequada, s'ha realitzat una comparativa entre **Moodle** i **Canvas LMS**.

---

## 3.1 Comparativa funcional i tècnica

| Característica | Moodle | Canvas |
|---|---|---|
| Cost | Gratuït | Pot tenir cost |
| Instal·lació | Mitjana | Més complexa |
| Facilitat d'ús | Bona | Molt bona |
| Comunitat | Molt gran | Menor |
| Escalabilitat | Alta | Alta |
| Funcionalitats educatives | Molt completes | Completes |

Moodle és una de les plataformes LMS més utilitzades a nivell mundial en entorns educatius.

Canvas destaca per la seva interfície moderna i experiència d'usuari millorada.

---

## 3.2 Experiència real durant el projecte

Durant el projecte també es van analitzar les dues plataformes des d’un punt de vista pràctic.

### Experiència amb Moodle

Aspectes positius:

- plataforma molt completa
- gran quantitat de plugins disponibles
- comunitat molt activa

Dificultats trobades:

- instal·lació inicial una mica més llarga
- interfície menys moderna

---

### Experiència amb Canvas

Aspectes positius:

- interfície molt moderna
- experiència d'usuari molt intuïtiva

Dificultats trobades:

- procés d’instal·lació més complex
- dependència d’alguns serveis externs

Aquestes experiències pràctiques han ajudat a valorar la viabilitat real de cada solució.

---

## 3.3 Mètriques i criteris observats

Durant el procés d'anàlisi es van tenir en compte diversos indicadors:

- Temps aproximat d'instal·lació de Moodle: **20–30 minuts**
- Procés de creació de cursos relativament senzill
- Gestió clara d'usuaris i rols

Canvas, en canvi, requeria més configuració inicial per començar a utilitzar el sistema.

---

## 3.4 Decisió final del LMS

La plataforma seleccionada per al projecte és **Moodle**.

### Justificació

Els principals motius de la decisió són:

- és programari lliure
- té una gran comunitat internacional
- ofereix moltes funcionalitats educatives
- és àmpliament utilitzat en universitats i centres de formació

Aquestes característiques fan que Moodle sigui una opció molt adequada per a la plataforma e-learning de Nexus.

---

# 4. Integració de la solució

La solució final integra les decisions tècniques preses durant el projecte.

## Arquitectura del sistema

La infraestructura proposada està formada per:

- **Sistema operatiu:** Ubuntu Server
- **Servidor web:** Nginx
- **LMS:** Moodle
- **Base de dades:** MariaDB o MySQL
- **Infraestructura:** VPS

Aquesta combinació permet construir una plataforma estable, escalable i eficient.

---

# 5. Viabilitat tècnica i econòmica

Per desplegar la infraestructura es proposa utilitzar un **servidor VPS europeu**, que permet reduir costos mantenint un bon nivell de rendiment.

## Proposta d’infraestructura

Característiques aproximades del VPS:

- 2 vCPU
- 4 GB RAM
- 80 GB SSD
- sistema operatiu Linux
- centre de dades europeu

---

## Proveïdors analitzats

Durant l'estudi es van considerar diversos proveïdors:

- OVHcloud
- Hetzner
- IONOS
- Scaleway

---

## VPS seleccionat

El proveïdor seleccionat és **Hetzner**.

### Motiu de la selecció

- preu competitiu
- bon rendiment dels servidors
- centres de dades situats a Europa

Cost aproximat:

- **8 € al mes**
- **96 € a l'any**

Aquest cost permet mantenir el projecte dins d’un pressupost raonable.

---

# 6. Qualitat, manteniment i sostenibilitat

Per garantir el correcte funcionament del sistema és necessari aplicar bones pràctiques de manteniment i seguretat.

## Manteniment del sistema

- actualització periòdica del sistema operatiu
- actualització de Moodle
- monitorització del rendiment del servidor

## Seguretat

- configuració de firewall
- ús de certificats HTTPS
- gestió adequada d’usuaris i permisos

## Sostenibilitat tecnològica

La solució adoptada contribueix a la sostenibilitat mitjançant:

- ús d’un servidor web eficient (Nginx)
- infraestructura VPS amb consum reduït
- optimització dels recursos del sistema

Aquest enfocament segueix els principis de **Green IT**.

---

# 7. Conclusions i proposta final

Després de l'anàlisi tècnica realitzada, la proposta final per al projecte Nexus és la següent:

- **Servidor web:** Nginx
- **Plataforma LMS:** Moodle
- **Sistema operatiu:** Ubuntu Server
- **Infraestructura:** VPS europeu (Hetzner)

Aquesta arquitectura ofereix diversos avantatges:

- bon rendiment del sistema
- costos d'infraestructura reduïts
- facilitat de manteniment
- possibilitat d'escalabilitat futura
- ús eficient dels recursos del servidor

Per aquests motius, aquesta solució es considera **la millor opció per desplegar la plataforma e-learning de Nexus de forma estable, eficient i sostenible**.
