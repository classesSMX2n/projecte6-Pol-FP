# Memòria Tècnica de Proposta
## Plataforma e-learning per a ProjecteNexus

---

# 1. Introducció

Aquest document presenta la proposta tècnica per al desplegament d’una plataforma d’aprenentatge en línia (LMS) per a l’empresa **ProjecteNexus**. L’objectiu del projecte és crear un entorn digital que permeti oferir formació tècnica en informàtica de manera accessible, flexible i escalable.

La solució proposada inclou la selecció de la plataforma LMS més adequada, el servidor web òptim per al seu funcionament i una infraestructura basada en un **VPS ubicat dins la Unió Europea** que garanteixi un bon rendiment, sostenibilitat i control de costos.

Aquest document integra:

- Comparativa tecnològica entre servidors web
- Comparativa entre plataformes LMS
- Estudi de sostenibilitat
- Proposta tècnica final
- Estimació de recursos i costos

---

# 2. Necessitats del client

Segons l’anàlisi del projecte, **ProjecteNexus** necessita una plataforma que permeti:

- Crear i gestionar cursos de formació tècnica
- Gestionar alumnes i professors
- Publicar contingut formatiu (documents, vídeos, exercicis)
- Realitzar avaluacions i seguiment de l’aprenentatge
- Permetre l’accés remot a través d’internet
- Garantir un bon rendiment amb costos moderats

També es valoren especialment els següents aspectes:

- Escalabilitat
- Facilitat d’administració
- Eficiència del servidor
- Baix consum de recursos

---

# 3. Comparativa de servidors web

Per a la implementació del LMS s’han analitzat dos servidors web molt utilitzats:

- Apache
- Nginx

## Apache

Apache és un dels servidors web més utilitzats del món i destaca per la seva flexibilitat i compatibilitat amb múltiples tecnologies.

### Avantatges

- Gran comunitat i documentació
- Compatible amb moltes aplicacions
- Configuració molt flexible
- Bona integració amb PHP

### Inconvenients

- Major consum de recursos en entorns amb molt trànsit
- Rendiment inferior amb moltes connexions simultànies

---

## Nginx

Nginx és un servidor web modern orientat a l’alt rendiment i a la gestió eficient de connexions.

### Avantatges

- Molt eficient en l’ús de recursos
- Millor rendiment amb moltes connexions simultànies
- Ideal per a aplicacions web modernes

### Inconvenients

- Configuració una mica més tècnica
- Menys flexibilitat en alguns casos

---

## Conclusió

Per a aquest projecte es recomana **Nginx**, ja que ofereix:

- millor rendiment
- menor consum de recursos
- millor adaptació a servidors VPS

Això permet reduir costos i millorar l’escalabilitat de la plataforma.

---

# 4. Comparativa de plataformes LMS

Per a la plataforma d’e-learning s’han analitzat diverses opcions de **Learning Management System (LMS)**:

- Moodle
- Canvas
- Chamilo

---

## Moodle

Moodle és una de les plataformes d’e-learning més utilitzades al món educatiu.

### Avantatges

- Programari lliure i gratuït
- Gran comunitat d’usuaris
- Gran quantitat de plugins disponibles
- Molt complet per a la gestió de cursos

### Inconvenients

- Interfície menys moderna
- Pot requerir més configuració inicial

---

## Canvas

Canvas és una plataforma LMS moderna molt utilitzada en universitats.

### Avantatges

- Interfície moderna
- Bona experiència d’usuari

### Inconvenients

- Algunes funcionalitats són de pagament
- Comunitat menor en instal·lacions autogestionades

---

## Chamilo

Chamilo és una plataforma LMS senzilla i fàcil d’utilitzar.

### Avantatges

- Instal·lació senzilla
- Consum baix de recursos

### Inconvenients

- Menys funcionalitats avançades
- Comunitat més reduïda

---

## Conclusió

La plataforma recomanada és **Moodle** perquè:

- és gratuïta
- és molt completa
- té una comunitat molt gran
- és molt utilitzada en formació tècnica

---

# 5. Estudi de sostenibilitat

La sostenibilitat del projecte s’ha analitzat des de diferents punts de vista.

## Eficiència energètica

L’ús d’un **VPS en centres de dades europeus** permet aprofitar infraestructures optimitzades amb consum energètic reduït.

## Optimització de recursos

L’ús de:

- servidor **Nginx**
- plataforma **Moodle**
- servidor **VPS escalable**

permet reduir el consum de CPU i memòria.

## Escalabilitat

El sistema permet ampliar recursos (CPU, RAM, disc) si augmenta el nombre d’alumnes.

---

# 6. Requisits del VPS

Per al correcte funcionament de la plataforma es recomanen els següents requisits mínims:

- **CPU:** 2 vCPU  
- **RAM:** 4 GB  
- **Disc:** 80 GB SSD  
- **Sistema operatiu:** Linux (Ubuntu Server)  
- **Amplada de banda:** mínim 1 Gbps  
- **Ubicació:** Unió Europea  

Aquests recursos permetran suportar una plataforma amb diversos cursos i diversos usuaris connectats.

---

# 7. Alternatives de VPS

S’han analitzat quatre proveïdors de VPS dins la Unió Europea.

## OVHcloud (França)

Característiques aproximades:

- 2 vCPU
- 4 GB RAM
- 80 GB SSD

Cost aproximat: **10–15 €/mes**

Avantatges:

- centre de dades europeu
- alta fiabilitat
- bona relació qualitat-preu

---

## Hetzner (Alemanya)

Característiques:

- 2 vCPU
- 4 GB RAM
- 80 GB SSD

Cost aproximat: **6–10 €/mes**

Avantatges:

- molt econòmic
- alt rendiment
- centres de dades a Alemanya i Finlàndia

---

## IONOS (Alemanya)

Característiques:

- 2 vCPU
- 4 GB RAM
- 80 GB SSD

Cost aproximat: **12–15 €/mes**

Avantatges:

- gran empresa europea
- bon suport tècnic

---

## Scaleway (França)

Característiques:

- 2 vCPU
- 4 GB RAM
- 80 GB SSD

Cost aproximat: **10–13 €/mes**

Avantatges:

- infraestructura moderna
- bona escalabilitat

---

# 8. Selecció del VPS

Després d’analitzar les alternatives, la proposta és utilitzar **Hetzner**.

## Justificació

Hetzner ofereix:

- el **cost més baix**
- **bon rendiment**
- centres de dades dins la **Unió Europea**
- alta fiabilitat

Això permet mantenir els costos reduïts sense comprometre el rendiment de la plataforma.

Cost estimat:

- **Servidor VPS:** aproximadament 8 €/mes
- **Cost anual aproximat:** 96 €/any

---

# 9. Estimació de feina

El desplegament de la plataforma es pot dividir en diverses fases:

| Fase | Tasca | Temps estimat |
|-----|------|------|
| 1 | Configuració del VPS | 2 hores |
| 2 | Instal·lació del sistema Linux | 1 hora |
| 3 | Instal·lació de Nginx i PHP | 2 hores |
| 4 | Instal·lació de Moodle | 2 hores |
| 5 | Configuració de cursos i usuaris | 3 hores |

**Temps total aproximat: 10 hores de treball tècnic**

---

# 10. Proposta final

La solució tècnica proposada per a **ProjecteNexus** consisteix en:

- **Plataforma LMS:** Moodle  
- **Servidor web:** Nginx  
- **Sistema operatiu:** Ubuntu Server  
- **Infraestructura:** VPS Hetzner  
- **Base de dades:** MariaDB o MySQL  

Aquesta combinació permet oferir una plataforma:

- eficient
- escalable
- amb baix cost
- fàcil d’administrar

---

# 11. Conclusió

El projecte proposat permet a **ProjecteNexus** disposar d’una plataforma d’e-learning robusta i sostenible per a la formació de tècnics informàtics.

La selecció de **Moodle**, **Nginx** i un **VPS europeu** garanteix una solució amb bon rendiment, costos reduïts i capacitat de creixement.

Aquesta infraestructura permetrà a l’empresa oferir cursos tècnics en línia de manera eficient, facilitant l’accés a la formació tecnològica i ampliant les possibilitats educatives del projecte.