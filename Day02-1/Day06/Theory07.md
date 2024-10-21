### Ce este standard input (intrare standard) în Java?

În programarea Java, **standard input** reprezintă metoda prin care un program primește date de la utilizator în timpul execuției. De obicei, acest input vine de la tastatură și este procesat de către program.

### Cum funcționează standard input în Java?

Java oferă mai multe moduri de a citi date de la utilizator. Unul dintre cele mai comune moduri este folosirea clasei `Scanner`, care ne permite să citim text, numere întregi, numere zecimale, valori booleene și altele direct de la tastatură.

### Pașii pentru a folosi standard input în Java:

1. **Importul clasei `Scanner`:** Pentru a folosi `Scanner`, trebuie să-l importăm din biblioteca `java.util`.
   ```java
   import java.util.Scanner;
   ```

2. **Crearea unui obiect `Scanner`:** După import, trebuie să creăm un obiect `Scanner` care va fi legat de intrarea standard (tastatură). Facem asta folosind `System.in`.
   ```java
   Scanner scanner = new Scanner(System.in);
   ```

3. **Citiți date de la utilizator:** Folosim metodele oferite de `Scanner` pentru a citi diferite tipuri de date de la utilizator.

### Exemplu simplu:

Să scriem un program simplu în care citim un nume, un număr întreg și un număr zecimal de la utilizator.

```java
import java.util.Scanner;

public class ExempluInputStandard {
    public static void main(String[] args) {
        // Creăm un obiect Scanner pentru a citi date de la tastatură
        Scanner scanner = new Scanner(System.in);
        
        // Citim un nume (text)
        System.out.print("Introdu numele tău: ");
        String nume = scanner.nextLine();
        
        // Citim un număr întreg
        System.out.print("Introdu un număr întreg: ");
        int numarIntreg = scanner.nextInt();
        
        // Citim un număr zecimal
        System.out.print("Introdu un număr zecimal: ");
        double numarZecimal = scanner.nextDouble();
        
        // Afișăm valorile citite
        System.out.println("Numele tău este: " + nume);
        System.out.println("Ai introdus numărul întreg: " + numarIntreg);
        System.out.println("Ai introdus numărul zecimal: " + numarZecimal);
        
        // Închidem obiectul Scanner
        scanner.close();
    }
}
```

### Explicația pașilor:

1. **Importul:** `import java.util.Scanner;` – importă clasa `Scanner` din biblioteca Java.
2. **Crearea Scanner-ului:** `Scanner scanner = new Scanner(System.in);` – creează un obiect `Scanner` care va citi de la tastatură.
3. **Citirea datelor:**
   - **Text:** `scanner.nextLine()` citește o linie întreagă de text introdusă de utilizator.
   - **Număr întreg:** `scanner.nextInt()` citește un număr întreg (fără zecimale).
   - **Număr zecimal:** `scanner.nextDouble()` citește un număr zecimal (cu virgulă, ex. 3.14).
4. **Afișarea datelor:** După ce citim valorile, le afișăm folosind `System.out.println()`.
5. **Închiderea Scanner-ului:** La final, închidem obiectul `Scanner` cu `scanner.close()` pentru a elibera resursele utilizate.

### Metode utile din `Scanner`:

- **`nextLine()`** – citește o întreagă linie de text.
- **`nextInt()`** – citește un număr întreg.
- **`nextDouble()`** – citește un număr zecimal.
- **`nextBoolean()`** – citește o valoare booleană (`true` sau `false`).
- **`next()`** – citește un cuvânt (până la primul spațiu sau Enter).

### De ce este importantă citirea de la tastatură?

Citirea datelor de la utilizator este esențială pentru a putea interacționa cu programele pe care le scrii. Astfel, poți crea programe care să fie flexibile și să răspundă la input-uri diferite. 

Acesta este un exemplu simplu de utilizare a standard input-ului în Java, dar poate fi extins pentru a citi și valida date mai complexe!

În Java, metoda `System.out.printf()` este utilizată pentru a formata și afișa text în consolă. Funcționează similar cu `System.out.print()` și `System.out.println()`, dar permite formatarea precisă a datelor, ceea ce este foarte util când vrei să controlezi cum arată ieșirea în funcție de tipul de date (numere întregi, zecimale, text etc.).

### Cum funcționează `printf()`?

Sintaxa generală a metodei `printf()` este:
```java
System.out.printf(format, arguments);
```
- **`format`**: Un șir de caractere (string) care conține textul ce va fi afișat și specificatori de formatare (ex.: `%d`, `%s`, `%f`).
- **`arguments`**: Lista de argumente care vor înlocui specificatorii de formatare.

### Specificatorii de formatare:

- **%d** – pentru numere întregi (int).
- **%f** – pentru numere zecimale (double).
- **%s** – pentru șiruri de caractere (String).
- **%c** – pentru caractere (char).
- **%b** – pentru valori booleene (boolean).

### Exemplu simplu de utilizare:

```java
public class ExempluPrintf {
    public static void main(String[] args) {
        // Afișarea unui text simplu
        String nume = "Adrian";
        System.out.printf("Salut, %s!%n", nume);

        // Afișarea unui număr întreg
        int varsta = 25;
        System.out.printf("Ai %d ani.%n", varsta);

        // Afișarea unui număr zecimal
        double greutate = 84.5;
        System.out.printf("Greutatea ta este %.2f kg.%n", greutate);

        // Afișarea unei valori booleene
        boolean esteStudent = false;
        System.out.printf("Este student? %b%n", esteStudent);
    }
}
```

### Explicația fiecărui element:

1. **`%s`** – se folosește pentru a afișa un șir de caractere (`String`). În exemplu, `%s` este înlocuit cu valoarea variabilei `nume`, care este `"Adrian"`.
2. **`%d`** – afișează un număr întreg (`int`). În exemplu, `%d` este înlocuit cu valoarea variabilei `varsta`, care este `25`.
3. **`%f`** – se folosește pentru numere zecimale (`double`). În exemplu, afișăm numărul `84.5` cu doar două zecimale, folosind `%.2f`.
4. **`%b`** – afișează o valoare booleană (`true` sau `false`).
5. **`%n`** – marchează o trecere la linia următoare (înlocuiește `\n`).

### Formatarea numerelor zecimale:

Poți controla câte zecimale sunt afișate cu ajutorul `%.Xf`, unde `X` este numărul de zecimale dorite.

Exemplu:
```java
double pi = 3.14159265359;
System.out.printf("Valoarea lui Pi cu două zecimale: %.2f%n", pi); // Afișează 3.14
```

### Formatarea aliniată:

Poți specifica o lățime minimă pentru a alinia textul. De exemplu, `%10s` va rezerva 10 caractere pentru un șir de caractere, aliniindu-l la dreapta.

```java
System.out.printf("%10s%n", "Salut"); // Afișează Salut aliniat la dreapta pe 10 caractere
```

### Exemple adiționale:

1. **Afișare mai complexă cu mai mulți parametri:**
   ```java
   int zi = 21, luna = 10, an = 2024;
   System.out.printf("Data de azi: %02d/%02d/%04d%n", zi, luna, an);
   ```
   Aici:
   - `%02d` înseamnă că numărul va fi afișat pe două caractere, completat cu `0` dacă este necesar (ex.: `01`, `02`).
   - `%04d` înseamnă că anul va fi afișat pe patru caractere.

2. **Alinierea numerelor:**
   ```java
   System.out.printf("%-10s %10d%n", "Item", 12345); // Aliniere la stânga pentru text și la dreapta pentru număr
   ```

### De ce să folosești `printf()`?

- **Control asupra formatului**: Poți controla exact cum vor fi afișate valorile (numărul de zecimale, lățimea minimă a câmpurilor, completarea cu zero-uri etc.).
- **Citibilitate mai bună**: În loc să folosești concatenări multiple de șiruri, poți să folosești `printf()` pentru a face codul mai curat și mai ușor de citit.
- **Compatibilitate cu alte limbaje**: `printf()` este similar cu funcția din limbaje precum C, ceea ce poate fi familiar pentru programatori care cunosc și alte limbaje.

Acum ai o bază solidă pentru a folosi `System.out.printf()` în Java!
