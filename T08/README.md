# T08: Vigilància i auditoria de sistemes 👁️‍🗨️

## Breu descripció

Un cop la infraestructura bàsica de **TransLògic S.A.** està completament operativa, la direcció de l'empresa ha expressat la seva preocupació per la **integritat de les dades** i la possibilitat d’**intrusions no detectades** dins del sistema.

En el sector de la **logística**, la informació és tan crítica com la mercaderia física. Per aquest motiu, no n’hi ha prou amb tenir una infraestructura funcional: també és imprescindible implementar mecanismes que permetin **monitoritzar el sistema i registrar tota l’activitat rellevant**.

Com a consultors tecnològics de confiança, se us ha encarregat implementar un sistema de **vigilància i auditoria**, capaç de detectar activitats sospitoses, intents d'accés no autoritzats i possibles incidents de seguretat.

L’objectiu d’aquesta tasca és configurar els **mecanismes de monitorització i registre del sistema (logs)** per poder analitzar posteriorment qualsevol comportament anòmal o atac potencial.

---

## Descripció de l'activitat

### 1️⃣ Monitorització de recursos del sistema 📊

El client vol assegurar-se que el servidor actual té **capacitat suficient per suportar la càrrega de treball** de l’empresa.

**Accions a realitzar:**

- Accedir al **Gestor de Tasques** o al **Monitor de Rendiment** del servidor.
- Realitzar una captura de pantalla on es mostri clarament:
  - l’ús de **CPU**
  - la **memòria RAM disponible**
- Interpretar breument aquestes dades.

**Objectiu:** determinar si el servidor està **saturat o treballa amb normalitat**.

---

### 2️⃣ Configuració d'auditoria de seguretat 🔐

Per detectar possibles **atacs de força bruta** (intents repetits d’endevinar contrasenyes), és necessari activar el registre d'esdeveniments relacionats amb l'inici de sessió.

**Accions a realitzar:**

- Configurar la **política d'auditoria de seguretat** mitjançant:
  - una **GPO**, o
  - la **política local del servidor**.
- Activar l’auditoria dels **esdeveniments d’inici de sessió**.
- Registrar tant:
  - **Èxits** (per saber qui accedeix al sistema)
  - **Fracassos** (per detectar intents d’accés no autoritzats)

---

### 3️⃣ Simulació d'incidents (Hacking ètic) 🧪

Un cop configurada l’auditoria, cal posar a prova el sistema simulant un possible intent d’intrusió.

**Procediment:**

1. Tancar la sessió actual.
2. Intentar iniciar sessió amb un usuari existent (per exemple, un usuari de **magatzem**) introduint **una contrasenya incorrecta**.
3. Repetir aquest intent **3 o 4 vegades**.
4. Finalment, iniciar sessió correctament amb **l’usuari administrador**.

Aquest procés generarà **esdeveniments de seguretat** que posteriorment podran ser analitzats.

---

### 4️⃣ Anàlisi forense amb Event Viewer 🔎

Després de la simulació, cal actuar com si fóssiu **pèrits informàtics** analitzant els registres del sistema.

**Accions a realitzar:**

- Obrir el **Visor d'Esdeveniments (Event Viewer)**.
- Accedir al registre de **Seguretat**.
- Localitzar els esdeveniments generats durant els intents fallits d'inici de sessió.
- Obrir un dels esdeveniments i analitzar els seus detalls, com ara:
  - l’usuari que ha intentat iniciar sessió
  - l’hora de l’intent
  - la possible IP d’origen

**Tasca d'investigació:**  
Identificar quin **Event ID** correspon als **intents fallits d’inici de sessió**.

---

## Què cal lliurar 📄

Cal elaborar un **Informe d'Auditoria** que inclogui:

### 1️⃣ Monitorització del sistema
- Captura dels recursos del sistema (CPU i RAM).
- Breu interpretació de l'estat del servidor.

### 2️⃣ Configuració d’auditoria
- Captura de la configuració de la política d’auditoria activada.

### 3️⃣ Evidència forense
- Captura clara del **Visor d'Esdeveniments** mostrant els errors d'inici de sessió generats durant la simulació.

### 4️⃣ Resposta tècnica
- Indicar quin és el **Event ID** que Windows assigna als **errors d'inici de sessió**.

---

## Material de suport 📚

- **0224 SOX — Material UD7: AA3**  
Disponible al **Moodle de l’assignatura**.