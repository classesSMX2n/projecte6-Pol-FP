# 1. Monitorització de recursos

En aquest apartat podem veure la quantitat de **RAM** i **CPU** que està utilitzant el nostre Windows Server.

![](img/01.png)

![](img/02.png)

Tal com es pot observar a les captures, el nostre **Windows Server està utilitzant aproximadament 2 GB de RAM dels 8 GB disponibles**.  

Pel que fa al **processador**, l’ús és molt baix i no es troba sota estrès. Encara qeu de vegades te pics

Això indica que el servidor disposa de **recursos suficients per realitzar les seves tasques sense problemes de rendiment**.

---

# 2. Configuració de la GPO per a l’auditoria de seguretat

En aquest apartat configurem una **política de grup (GPO)** per auditar els intents d’inici de sessió al sistema.

Activem la política perquè **registri tant els intents d’inici de sessió correctes com els fallits**.

D’aquesta manera, el sistema guardarà informació al visor d’esdeveniments cada vegada que un usuari intenti iniciar sessió.

![](img/03.png)

---

# 3. Simulació d’un incident de seguretat

Per comprovar que la política d’auditoria funciona correctament, realitzem una petita simulació:

1. Intentem iniciar sessió amb un usuari introduint **una contrasenya incorrecta**.
2. Posteriorment, iniciem sessió correctament amb **l’usuari administrador**.

Després d’això, accedim al **Event Viewer (Visor d’esdeveniments)** per comprovar si el sistema ha registrat aquests intents d’inici de sessió.

![](img/04.png)

![](img/05.png)

---

# 4. Anàlisi dels resultats

Un cop revisats els logs al **Visor d’esdeveniments**, podem observar diferents registres relacionats amb els intents d’inici de sessió.

En concret, trobem l’**Event ID 4625**, que indica un **intent d’inici de sessió fallit**.

Aquest registre ens mostra informació important com:

- l’usuari que ha intentat iniciar sessió
- l’hora de l’intent
- l’equip des del qual s’ha fet l’intent
- el motiu pel qual ha fallat l’autenticació

Aquesta informació és molt útil per **detectar possibles intents d’accés no autoritzat al sistema**.

---

# 5. Resposta tècnica

L’**Event ID 4625** correspon a un **intent d’inici de sessió fallit (Failed Logon)**.

Aquest tipus d’esdeveniment es registra quan un usuari intenta accedir al sistema però la **validació de credencials no és correcta**, per exemple quan s’introdueix una contrasenya incorrecta.

Gràcies a aquesta auditoria, els administradors poden **monitoritzar i detectar possibles incidents de seguretat**.