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
