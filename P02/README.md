# P02 – Presentació de la proposta al client
## Projecte Nexus – Plataforma E-learning

---

# 1. Presentació de la consultora

Som un equip tècnic especialitzat en **infraestructures de sistemes i serveis web** orientats a projectes educatius i tecnològics.

La nostra tasca en aquest projecte ha estat:

- Analitzar les necessitats de l'empresa Nexus
- Estudiar diferents tecnologies possibles
- Desplegar i provar solucions reals
- Comparar alternatives tècniques
- Proposar una infraestructura viable i sostenible

El nostre objectiu és oferir una **solució fiable, escalable i econòmica** per a la nova plataforma e-learning de Nexus.

---

# 2. Context i necessitats del client

L'empresa **Nexus e-learning** vol crear una plataforma de formació online orientada a **cursos per a tècnics informàtics**.

Per tal que el projecte sigui viable, la infraestructura ha de complir diversos requisits:

### Rendiment
La plataforma ha de suportar diversos usuaris connectats simultàniament sense perdre velocitat.

### Cost controlat
El projecte està pensat per una petita o mitjana organització, per tant cal una solució amb **costos moderats**.

### Sostenibilitat
La infraestructura ha d'utilitzar els recursos de forma eficient per reduir el consum energètic.

### Facilitat de manteniment
El sistema ha de ser fàcil d'administrar i mantenir per l'equip tècnic.

---

# 3. T04 – Duel de titans: Apache vs Nginx

## Comparativa tècnica

| Característica | Apache | Nginx |
|---|---|---|
| Instal·lació | Senzilla | Senzilla |
| Configuració | Flexible | Més tècnica |
| Rendiment | Bo | Molt alt |
| Consum de recursos | Mitjà | Baix |
| Escalabilitat | Bona | Molt bona |

---

## Experiència real durant el projecte

Durant les proves pràctiques es van observar diversos aspectes:

### Apache

Avantatges observats:

- Configuració molt flexible
- Gran quantitat de documentació

Dificultats trobades:

- Consum de memòria més elevat
- Configuració més complexa en alguns casos

---

### Nginx

Avantatges observats:

- Configuració clara
- Millor rendiment en el servidor

Dificultats trobades:

- Menys flexible que Apache
- Algunes configuracions requereixen més coneixement tècnic

---

## Mètriques observades

Encara que siguin orientatives, durant les proves es van observar:

- Temps instal·lació Apache: ~10 minuts
- Temps instal·lació Nginx: ~8 minuts
- Consum aproximat de RAM:
  - Apache: més alt
  - Nginx: més baix

També es va observar que **Nginx responia més ràpid en proves amb múltiples connexions**.

---

## Decisió final – Servidor web

La tecnologia escollida és **Nginx**.

### Justificació

- Millor rendiment
- Consum menor de recursos
- Ideal per entorns VPS
- Millor eficiència energètica

Aquesta decisió respon millor a les necessitats de **rendiment i sostenibilitat del client**.

---

# 4. T11 – Comparativa Moodle vs Canvas

## Comparativa funcional

| Característica | Moodle | Canvas |
|---|---|---|
| Cost | Gratuït | Pot tenir cost |
| Instal·lació | Mitjana | Més complexa |
| Funcionalitats educatives | Molt completes | Completes |
| Comunitat | Molt gran | Menor |
| Escalabilitat | Alta | Alta |

---

## Experiència real durant el projecte

### Moodle

Aspectes positius:

- Plataforma molt completa
- Gran nombre de plugins
- Comunitat molt activa

Dificultats trobades:

- Configuració inicial més llarga
- Interfície menys moderna

---

### Canvas

Aspectes positius:

- Interfície moderna
- Experiència d'usuari molt bona

Dificultats trobades:

- Instal·lació més complexa
- Algunes funcionalitats depenen de serveis externs

---

## Mètriques observades

Durant les proves es van observar:

- Temps instal·lació Moodle: ~20-30 minuts
- Creació d'un curs: relativament senzilla
- Gestió d'usuaris: clara i estructurada

Canvas requeria més configuració inicial.

---

## Decisió final – LMS

La plataforma seleccionada és **Moodle**.

### Justificació

- Programari lliure
- Gran comunitat
- Moltes funcionalitats educatives
- Molt utilitzat en entorns acadèmics

És una solució ideal per una plataforma de formació tècnica com Nexus.

---

# 5. Integració de la solució

La infraestructura final combina les dues decisions principals:

### Servidor web
Nginx

### Plataforma E-learning
Moodle

### Sistema operatiu
Ubuntu Server

### Base de dades
MariaDB / MySQL

Aquesta combinació permet construir una plataforma **eficient, estable i escalable**.

---

# 6. Viabilitat tècnica i econòmica

Per desplegar la solució es proposa utilitzar un **VPS europeu**.

## Proposta d'infraestructura

Característiques del VPS:

- 2 vCPU
- 4 GB RAM
- 80 GB SSD
- Sistema Linux
- Ubicació UE

---

## Proveïdors analitzats

- OVHcloud
- Hetzner
- IONOS
- Scaleway

---

## VPS seleccionat

**Hetzner**

### Motius

- Cost reduït
- Bon rendiment
- Centres de dades europeus

Cost aproximat:

- 8 €/mes
- 96 €/any

---

# 7. Estimació de temps i implantació

| Fase | Tasca | Temps |
|---|---|---|
| Preparació | Configuració VPS | 2 hores |
| Sistema | Instal·lació Linux | 1 hora |
| Servidor web | Instal·lació Nginx | 2 hores |
| Plataforma | Instal·lació Moodle | 2 hores |
| Configuració | Usuaris i cursos | 3 hores |

Temps total estimat: **10 hores**

---

# 8. Qualitat, manteniment i sostenibilitat

Per garantir el bon funcionament del sistema es proposen diverses mesures.

### Manteniment

- Actualitzacions del sistema
- Monitorització del servidor
- Revisió periòdica del rendiment

### Seguretat

- Configuració de firewall
- Certificat HTTPS
- Gestió d'usuaris

### Sostenibilitat

- Servidor eficient (Nginx)
- Infraestructura VPS
- Consum reduït de recursos

Aquest enfocament s'alinea amb els principis de **Green IT**.

---

# 9. Conclusions

La solució proposada per al projecte Nexus consisteix en:

- Plataforma LMS: **Moodle**
- Servidor web: **Nginx**
- Infraestructura: **VPS europeu (Hetzner)**

Aquesta arquitectura ofereix:

- bon rendiment
- costos controlats
- escalabilitat futura
- consum eficient de recursos

Per aquests motius considerem que aquesta és **la millor opció per al desplegament de la plataforma e-learning de Nexus**.