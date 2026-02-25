# T05: Top Secret, protegint els secrets 🔒

## Breu descripció

Aprofitant que ja esteu treballant amb la infraestructura web del client, **Projecte Nexus** ens sol·licita una nova petició d’ajuda.  
A causa del gran volum de **dades sensibles** que gestionen (dades personals d'estudiants, exàmens oficials no publicats i certificats de notes), la seva preocupació principal és **la integritat i privacitat de la informació**.  

La direcció de Projecte Nexus demana una **demostració pràctica** que garanteixi els tres pilars de la seguretat de la informació:  

- **Confidencialitat**  
- **Integritat**  
- **Autenticitat**

---

## Descripció de l'activitat

### Tasca 1: Protecció de dades en repòs (Xifratge Simètric) 🗄️

Els caps de departament necessiten transportar els exàmens finals en memòries USB per imprimir-los, però tenen por de perdre el dispositiu i que les preguntes es filtrin abans de la prova.  

**Objectiu:** Crear un **contenidor xifrat** (unitat virtual) dins d'un pendrive simulat al disc dur amb **VeraCrypt** o un programari similar.  

**Requisits:**

- Crear un volum de **100MB**  
- Utilitzar l’algorisme de xifratge **AES-256**  
- Establir una **contrasenya robusta**  
- Dins la unitat xifrada, copiar un fitxer **EXAMEN_FINAL_SEGURETAT.txt** amb preguntes de prova  
- Demostrar que, sense muntar la unitat amb la contrasenya, el fitxer és **inaccessible**

---

### Tasca 2: Verificació d'Integritat (Hashing) 📝

Nexus distribueix material didàctic i software als alumnes i vol garantir que els fitxers **no han estat alterats** per atacants que podrien afegir malware.  

**Procediment:**  

- Crear un fitxer de text **nota_final_curs.txt** amb el contingut: `"L'alumne ha aprovat amb un 5"`  
- Calcular el **Hash SHA-256** del fitxer original  
- Modificar el fitxer canviant una xifra (ex: `"L'alumne ha aprovat amb un 9"`)  
- Tornar a calcular el hash i **comparar els resultats** per demostrar com l’empremta digital canvia i revela la manipulació

---

## Què cal lliurar 📄

Heu de redactar un **informe tècnic en Markdown** que contingui:

### 1️⃣ Justificació Teòrica
Breu explicació (màxim 10 línies) per al client de la diferència entre:

- **Xifratge:** amaga la informació  
- **Funció hash:** garanteix la **integritat** del fitxer

### 2️⃣ Evidències de la Tasca 1
- Captura de pantalla de la configuració del volum (algorisme escollit)  
- Captura de la unitat muntada amb l'examen secret a dins  
- Captures del procés d’accés al fitxer

### 3️⃣ Evidències de la Tasca 2
- Captura de pantalla del terminal o programa mostrant els **dos hashos** (original i modificat) per veure la diferència

### 4️⃣ Conclusió
Breu recomanació final a **Nexus**:

- La importància de protegir les dades, especialment **les portables amb xifratge**  
- Gestió segura de les **contrasenyes** (robustesa i emmagatzematge)  
- Necessitat d’utilitzar **hash** per assegurar la integritat de documentació crítica com actes de notes, contractes, etc.

---

## Material de suport 📚

- Material de l’assignatura **Seguretat Informàtica. RA3. Introducció a la criptografia** [Moodle de l’assignatura]  
- Tutorial **VeraCrypt**: [https://veracrypt.io/en/Beginner's%20Tutorial.html](https://veracrypt.io/en/Beginner's%20Tutorial.html)