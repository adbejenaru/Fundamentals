Un data type (tip de date) reprezintă o clasificare care indică ce tip de valoare poate stoca o variabilă într-un program și ce operații pot fi efectuate asupra acelor date. Fiecare limbaj de programare, inclusiv Java, are mai multe tipuri de date predefinite care ajută la stocarea și manipularea informațiilor într-o formă eficientă și organizată.

```java
public class TipuriDeDate {
    public static void main(String[] args) {
        // Tipuri numerice (integer)
        int varsta = 30; // variabilă întreg
        long distanta = 123456789L; // variabilă de tip long (întreg pe 64 de biți)

        // Tipuri numerice (floating point)
        float greutate = 65.5f; // variabilă float (cu virgulă mobilă)
        double inaltime = 1.75; // variabilă double (cu virgulă mobilă, mai precisă)

        // Tip boolean
        boolean esteAdult = true; // variabilă boolean (true sau false)

        // Tip caracter
        char initiala = 'A'; // variabilă de tip char (un singur caracter)

        // Tip string
        String nume = "Maria"; // variabilă String (șir de caractere)

        // Afișăm valorile variabilelor
        System.out.println("Nume: " + nume); 
        System.out.println("Vârsta: " + varsta + " ani");
        System.out.println("Distanță: " + distanta + " metri");
        System.out.println("Greutate: " + greutate + " kg");
        System.out.println("Înălțime: " + inaltime + " metri");
        System.out.println("Este adult? " + esteAdult);
        System.out.println("Inițiala: " + initiala);
    }
}
```

### Explicația codului:
1. **Tipuri numerice:**
   - `int varsta = 30;` – stocăm un număr întreg.
   - `long distanta = 123456789L;` – folosim un număr mai mare stocat într-un `long`.

2. **Numere cu virgulă (floating point):**
   - `float greutate = 65.5f;` – stocăm o valoare cu virgulă (kilograme).
   - `double inaltime = 1.75;` – un număr mai precis cu virgulă pentru înălțime.

3. **Boolean:**
   - `boolean esteAdult = true;` – folosim un tip boolean pentru a reprezenta o condiție de tip "adevărat" sau "fals".

4. **Caractere:**
   - `char initiala = 'A';` – stocăm un singur caracter, în acest caz inițiala numelui.

5. **String:**
   - `String nume = "Maria";` – stocăm un șir de caractere (un nume).

### Output-ul acestui program ar fi:
```
Nume: Maria
Vârsta: 30 ani
Distanță: 123456789 metri
Greutate: 65.5 kg
Înălțime: 1.75 metri
Este adult? true
Inițiala: A
```

Acest exemplu pune în practică toate tipurile de date explicate, folosindu-le pentru a stoca și afișa informații despre o persoană.


Slide-ul explică faptul că Java este un limbaj de programare **statically typed**, ceea ce înseamnă că tipurile de variabile sunt verificate la momentul compilării și trebuie declarate înainte de a fi utilizate. Să descompunem această idee:

### 1. **Tipurile variabilelor sunt determinate în timpul compilării**
   - În Java, tipurile de date ale variabilelor trebuie specificate **înainte de rularea programului**. Compilatorul verifică aceste tipuri în timpul compilării (înainte ca programul să fie executat). 
   - **Exemplu**:
     ```java
     int varsta = 25; // Tipul 'int' este declarat explicit la compilare
     ```

   - Dacă încerci să atribui un alt tip de date (de exemplu, un `String` unui `int`), programul nu va trece de compilare și va da o eroare.

### 2. **Este ușor să detectezi erorile în timpul compilării**
   - Deoarece tipurile sunt verificate la compilare, erorile legate de utilizarea incorectă a tipurilor de date pot fi identificate **înainte** ca programul să fie executat. Acest lucru ajută la prevenirea unor posibile probleme de runtime și îmbunătățește fiabilitatea programului.
   - **Exemplu de eroare**:
     ```java
     int varsta = "douăzeci"; // Eroare de compilare - nu poți atribui un string unei variabile int
     ```

### 3. **Tipurile de variabile trebuie declarate înainte de inițializare**
   - În Java, trebuie să **declari** tipul unei variabile înainte să îi atribui o valoare. Asta înseamnă că nu poți folosi o variabilă fără să-i spui compilatorului ce tip de date va stoca.
   - **Exemplu corect**:
     ```java
     double inaltime;
     inaltime = 1.75; // Mai întâi declari variabila, apoi o inițializezi
     ```

   - **Exemplu incorect**:
     ```java
     inaltime = 1.75; // Eroare - nu ai declarat tipul variabilei 'inaltime'
     ```

### Avantajele unui limbaj tipizat static:
   - **Siguranță**: Erorile legate de tipuri sunt detectate devreme, prevenind probleme în timpul execuției.
   - **Claritate**: Tipurile declarate clarifică pentru toți dezvoltatorii ce tip de date sunt așteptate, îmbunătățind lizibilitatea codului.
   - **Performanță**: Deoarece compilatorul cunoaște tipurile de date în avans, poate optimiza executarea programului.

În concluzie, Java fiind un limbaj **statically typed** impune ca toate variabilele să aibă tipurile lor clar definite înainte de utilizare. Această caracteristică face mai ușoară detectarea erorilor și asigură că programul funcționează corect, prevenind probleme de tip în timpul execuției.
