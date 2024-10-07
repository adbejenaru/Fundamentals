Pentru începători, variabilele sunt un concept de bază în programare. Ele sunt ca niște **cutiuțe** în care putem **stoca informații** (date) pentru a le folosi mai târziu în program. De exemplu, dacă vrei să reții un număr, un text, sau alte tipuri de informații, poți folosi variabile.

### Ce trebuie să știi despre variabile:
1. **Denumirea unei variabile** – fiecare variabilă trebuie să aibă un nume unic. Acesta poate fi ales de tine și trebuie să fie clar, ca să știi ce informație stochează.
   
   De exemplu, dacă vrei să stochezi vârsta unei persoane, poți să denumești variabila `varsta`.

2. **Tipul variabilei** – în Java (și în alte limbaje de programare), variabilele trebuie să aibă un tip specific, care indică ce fel de date stochează.
   - **int** pentru numere întregi.
   - **double** pentru numere cu virgulă.
   - **String** pentru texte.

3. **Inițializarea unei variabile** – atunci când declari o variabilă, poți să îi dai și o valoare inițială. 

### Cum declarăm o variabilă?

Pentru a declara și folosi o variabilă, urmezi acest format:
```java
Tip NumeVariabila = Valoare;
```

### Exemple simple:

1. **Variabilă de tip întreg**:
   ```java
   int varsta = 25; // Am creat o variabilă numită "varsta" și am stocat în ea valoarea 25.
   ```
   
2. **Variabilă de tip text (String)**:
   ```java
   String nume = "Maria"; // Am creat o variabilă numită "nume" și am stocat în ea textul "Maria".
   ```

3. **Variabilă de tip număr cu virgulă (double)**:
   ```java
   double inaltime = 1.75; // Am creat o variabilă numită "inaltime" și am stocat în ea valoarea 1.75.
   ```

### De ce sunt utile variabilele?
Variabilele ne permit să **salvăm informații** și să le **folosim mai târziu** în program. De exemplu, dacă vrei să calculezi suma a două numere, poți salva acele numere în variabile și apoi să le aduni.

### Exemplu complet:
```java
public class Exemplu {
    public static void main(String[] args) {
        int varsta = 25;        // Declaram variabila "varsta" și îi dăm valoarea 25
        String nume = "Maria";  // Declaram variabila "nume" și îi dăm valoarea "Maria"

        System.out.println(nume + " are " + varsta + " ani.");
        // Afișăm: "Maria are 25 ani."
    }
}
```

În concluzie, variabilele sunt ca niște **spații temporare de stocare** unde păstrăm date, pentru a le folosi în programele noastre.
