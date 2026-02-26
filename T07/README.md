# T07: TransLògic: Administració Avançada i Seguretat Corporativa 🏢

## Breu descripció

TransLògic S.A., empresa logística amb infraestructura basada en **Directori Actiu**, requereix millores crítiques per garantir la **seguretat corporativa, gestió eficient del programari i mobilitat dels usuaris**.  
La direcció està preocupada per:

- La seguretat de les **contrasenyes**  
- La **mobilitat** dels treballadors entre diferents equips  
- La **gestió controlada** d’un assistent tècnic sense privilegis complets d’administrador  

L’objectiu d’aquesta tasca és implementar mesures avançades de **seguretat, automatització i administració** que permetin un entorn estable, segur i eficient.

---

## Descripció de l'activitat

### 1️⃣ Polítiques de Seguretat i Contrasenyes 🔐

**Objectiu:** Endurir la política de contrasenyes per tot el domini i per grups específics.

**Accions:**

- **Política global:** Modificar la Default Domain Policy perquè **tots els membres del domini** tinguin contrasenya mínima de 8 caràcters.  
- **Política per a Gerència:** Crear una **GPO específica** per a l’OU amb usuaris VIP (grup gerencia) amb contrasenya de 18 caràcters, caducitat cada 28 dies i sense complexitat obligatòria.  
- **Millora proactiva (Bonus):** Proposar i implementar una tercera GPO útil per a l’empresa logística (ex: bloqueig automàtic de pantalla, fons d’escriptori corporatiu, restriccions específiques, etc.) amb justificació tècnica.

---

### 2️⃣ Desplegament Automatitzat de Programari 📦

**Objectiu:** Reduir tiquets de suport tècnic i garantir que cada departament disposi de les eines necessàries.

**Accions:**

- **Departament de Gestió:** Instal·lar automàticament **7zip** amb GPO assignada als administratius (grup gestio).  
- **Departament de Gerència:** Proporcionar **Firefox** amb GPO publicada perquè els directius decideixin instal·lar-lo des del Tauler de Control.  
- **Pregunta de consultoria:** Explicar com crear fitxers **.msi** a partir d’un **.exe** per a futures implementacions.

---

### 3️⃣ Mobilitat d’Usuaris (Perfils Mòbils) 💻

**Objectiu:** Permetre que els usuaris del grup gestio puguin iniciar sessió en qualsevol dispositiu sense perdre configuració ni dades.

**Accions:**

- Habilitar una **carpeta compartida "perfils"** al servidor.  
- Configurar els perfils mòbils dels usuaris del grup gestio per desar les dades a aquesta carpeta.  
- Crear un usuari de prova, iniciar sessió i verificar que el perfil es crea correctament al servidor.

---

### 4️⃣ Seguretat de Dades (Redirecció de Carpetes) 💾

**Objectiu:** Evitar pèrdues de dades en cas de fallada d’un ordinador.

**Accions:**

- Configurar directiva per redirigir la carpeta **Documents** local a la ubicació de xarxa segura corresponent al **home folder** de cada usuari.  
- Verificar que els fitxers desats a "Documents" es reflecteixen correctament al servidor.

---

### 5️⃣ Delegació de Funcions (Helpdesk) 🧑‍💻

**Objectiu:** Assignar responsabilitats limitades a un auxiliar de suport sense comprometre la seguretat global.

**Accions:**

- Crear usuari **adminOU** dins la OU d’usuaris.  
- Delegar el control de la OU principal (**OU TransLogic**) perquè adminOU només pugui:  
  - Reiniciar contrasenyes dels treballadors  
  - Modificar la pertinença als grups (gestio, magatzem, etc.)  
- Demostrar amb captures que **no pot crear nous usuaris**.

---

## Què cal lliurar 📄

- Informe tècnic amb **canvis en l’estructura d’OU** i justificació.  
- Captures de pantalla comentades de cada pas: GPO creades, configuracions de perfils, logs d’auditoria, etc.  
- **Justificació de la tercera GPO:** Explicació del benefici aportat.  
- **Resposta sobre els fitxers MSI:** Breu explicació de com convertir o crear paquets MSI.  
- **Proves de funcionament:** Captures demostrant l’aplicació correcta de polítiques, redirecció de carpetes i restriccions d’adminOU.

---

## Material de suport 📚

- **0224 SOX. Material UD7: AA1, AA2 i AA4** [Moodle de l’assignatura]