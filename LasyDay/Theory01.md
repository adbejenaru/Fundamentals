În Java (și în alte limbaje de programare), structura de control **`do-while`** este o variantă a buclei `while`, care execută codul din buclă cel puțin o dată, indiferent de condiție.

### Structura `do-while`

Sintaxa pentru o buclă `do-while` este:

```java
do {
    // Codul care se va executa cel puțin o dată
} while (condiție);
```

### Cum funcționează?

1. **Codul din interiorul blocului `do`** se execută cel puțin o dată.
2. După ce execută codul din interior, **condiția este verificată**.
3. Dacă **condiția este `true`**, bucla se repetă, iar codul din interior se execută din nou.
4. Dacă **condiția este `false`**, bucla se oprește și programul continuă cu instrucțiunile de după bucla `do-while`.

### Diferența față de `while`

Diferența principală dintre `do-while` și `while` este ordinea execuției:
- În `while`, condiția este verificată **la început**. Dacă condiția este `false` de la început, codul din buclă nu se execută deloc.
- În `do-while`, codul se execută **cel puțin o dată** înainte de a verifica condiția.

### Exemplu de utilizare

```java
int număr = 1;

do {
    System.out.println("Numărul este: " + număr);
    număr++;
} while (număr <= 5);
```

**Explicație**:
- Bucla `do-while` începe prin a afișa valoarea variabilei `număr`, apoi mărește valoarea acesteia cu `1`.
- După executarea codului, verifică dacă `număr <= 5`.
- Cât timp condiția este adevărată (`true`), bucla se repetă.
- Când `număr` devine `6`, condiția devine falsă (`false`), iar bucla se oprește.

**Rezultatul afișat**:
```
Numărul este: 1
Numărul este: 2
Numărul este: 3
Numărul este: 4
Numărul este: 5
```

### Când să folosești `do-while`?

`do-while` este utilă atunci când:
- Vrei ca instrucțiunile să se execute cel puțin o dată, indiferent de condiție.
- Condiția de oprire trebuie verificată **după** executarea codului. 

Un exemplu comun este atunci când soliciți o valoare de la utilizator și vrei să continui solicitarea până când este introdusă o valoare validă.

Un exemplu practic al buclei `do-while` este atunci când ceri utilizatorului să introducă o valoare validă și continui solicitarea până când aceasta respectă anumite condiții, de exemplu, introducerea unui număr între 1 și 10.

Iată cum ar arăta acest exemplu:

```java
import java.util.Scanner;

public class ExempluDoWhile {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int numar;

        do {
            System.out.print("Introdu un număr între 1 și 10: ");
            numar = scanner.nextInt();
            
            if (numar < 1 || numar > 10) {
                System.out.println("Numărul nu este valid. Încearcă din nou.");
            }
        } while (numar < 1 || numar > 10);

        System.out.println("Ai introdus un număr valid: " + numar);
    }
}
```

### Explicație:

1. Programul cere utilizatorului să introducă un număr între 1 și 10.
2. Codul din blocul `do` se execută **cel puțin o dată**, indiferent de valoarea introdusă.
3. Dacă numărul introdus nu este în intervalul 1-10, programul afișează un mesaj de eroare și cere din nou introducerea unui număr.
4. **Condiția `while`** verifică dacă numărul este în afara intervalului. Cât timp această condiție este adevărată, bucla continuă.
5. Când utilizatorul introduce un număr între 1 și 10, condiția devine `false`, iar bucla se oprește, afișând mesajul de confirmare.

### Exemplu de rulare:

```
Introdu un număr între 1 și 10: 15
Numărul nu este valid. Încearcă din nou.
Introdu un număr între 1 și 10: -3
Numărul nu este valid. Încearcă din nou.
Introdu un număr între 1 și 10: 7
Ai introdus un număr valid: 7
```

### Când este util acest exemplu?
Acest tip de buclă `do-while` este folosit pentru validarea input-ului de la utilizator, asigurându-te că valoarea introdusă este corectă înainte de a continua programul.
