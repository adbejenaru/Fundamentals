Să luăm programul pas cu pas și să explicăm fiecare parte din codul Java:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### 1. `public class HelloWorld`
Aceasta definește o **clasă** în Java. În Java, totul este organizat în clase, care sunt șabloane pentru crearea obiectelor. În cazul acesta, clasa este numită `HelloWorld`, și aceasta trebuie să fie numită la fel ca fișierul în care se află (de exemplu, `HelloWorld.java`).

- **public**: Înseamnă că această clasă poate fi accesată din orice altă parte a programului.
- **class**: Este un cuvânt cheie care definește o clasă.
- **HelloWorld**: Este numele clasei.

### 2. `public static void main(String[] args)`
Aceasta este **metoda principală** (sau punctul de intrare) al programului. Când rulezi un program Java, execuția începe de la metoda `main`.

- **public**: Înseamnă că metoda poate fi accesată de oriunde în program.
- **static**: Înseamnă că această metodă aparține clasei și nu unui obiect instanțiat al clasei.
- **void**: Aceasta indică faptul că metoda nu returnează nicio valoare.
- **main**: Este numele metodei principale, care este punctul de start al programului.
- **String[] args**: Acesta este un parametru care permite programului să primească argumente de comandă sub formă de șiruri de caractere. Dacă rulezi programul din linia de comandă și adaugi argumente, acestea vor fi disponibile în acest array `args`.

### 3. `System.out.println("Hello, World!");`
Aceasta este instrucțiunea care afișează mesajul "Hello, World!" pe ecran.

- **System**: Este o clasă predefinită în Java, care oferă acces la funcții și metode de bază pentru interacțiunea cu sistemul.
- **out**: Este un obiect al clasei `System`, care este folosit pentru a trimite date la consola (ecran).
- **println()**: Este o metodă care afișează textul pe consolă, urmat de un caracter de linie nouă (adică trece pe linia următoare după afișarea textului).
- `"Hello, World!"`: Acesta este șirul de caractere care va fi afișat pe ecran.

### Cum rulezi programul?
1. **Scrie codul** într-un fișier numit `HelloWorld.java`.
2. **Compilează-l** folosind comanda:
   ```bash
   javac HelloWorld.java
   ```
   Aceasta va genera un fișier `HelloWorld.class`, care conține codul compilat.
3. **Rulează-l** folosind comanda:
   ```bash
   java HelloWorld
   ```
   Aceasta va afișa pe ecran:
   ```
   Hello, World!
   ```

### De ce e important acest program?
- Îți arată structura de bază a unui program Java: o clasă și o metodă principală.
- Îți oferă primul contact cu sintaxa Java: cum definești clase, metode și cum interacționezi cu consola.
- Este primul pas în înțelegerea modului în care funcționează Java, un limbaj orientat pe obiecte.

Aceasta este baza, și de aici poți învăța concepte mai avansate cum ar fi variabilele, buclele, condițiile și programarea orientată pe obiecte.


### Ce sunt variabilele în programare

Variabilele sunt un concept de bază în programare. Ele sunt ca niște **cutiuțe** în care putem **stoca informații** (date) pentru a le folosi mai târziu în program. De exemplu, dacă vrei să reții un număr, un text sau alte tipuri de informații, poți folosi variabile.

### Declarația variabilelor în Java (Slide 1)

În Java, pentru a folosi o variabilă, mai întâi trebuie să o **declari**. Declarația specifică tipul variabilei și îi dă un nume, care va fi folosit pentru a face referire la acea variabilă în program. 

#### Structura generală pentru declarația unei variabile:
```java
{modificator de acces} {tip variabilă} {nume variabilă};
```

**Exemplu:**
```java
private int number;
```
- `private` este **modificatorul de acces**, care limitează accesul la variabilă doar la interiorul clasei în care a fost definită.
- `int` este **tipul de date** al variabilei, în acest caz un număr întreg.
- `number` este **numele variabilei**, care o identifică în program.

### Ce trebuie să știi despre variabile:

1. **Denumirea variabilei** – fiecare variabilă trebuie să aibă un **nume unic**, pe care îl alegi astfel încât să fie clar ce informație stochează. De exemplu, dacă vrei să stochezi vârsta unei persoane, poți să denumești variabila `varsta`.

2. **Tipul variabilei** – variabilele în Java trebuie să aibă un **tip specific** de date, care indică ce fel de informații vor stoca:
   - `int` pentru numere întregi.
   - `double` pentru numere cu virgulă.
   - `String` pentru texte.

### Inițializarea variabilei în Java (Slide 2)

După ce o variabilă a fost declarată, ea trebuie **inițializată**, adică trebuie să i se atribuie o valoare. Inițializarea se face folosind operatorul `=`.

#### Cum se inițializează o variabilă:
```java
numeVariabilă = valoare;
```

**Exemplu:**
```java
number = 5;
```
Aici:
- `number` este variabila declarată anterior.
- `=` este operatorul de atribuire.
- `5` este valoarea care este stocată în variabilă.

### Exemple de variabile:

1. **Variabilă de tip întreg:**
   ```java
   int varsta = 25; // Declarație și inițializare pentru un număr întreg
   ```

2. **Variabilă de tip text (String):**
   ```java
   String nume = "Maria"; // Declarație și inițializare pentru un text
   ```

3. **Variabilă de tip număr cu virgulă (double):**
   ```java
   double inaltime = 1.75; // Declarație și inițializare pentru un număr zecimal
   ```

### Utilitatea variabilelor

Variabilele sunt utile pentru a **salva informații** și a le **folosi mai târziu** în program. De exemplu, dacă vrei să calculezi suma a două numere, poți salva acele numere în variabile și apoi să le aduni.

### Exemplu complet:
```java
public class Exemplu {
    public static void main(String[] args) {
        int varsta = 25;        // Declarația și inițializarea unei variabile întregi
        String nume = "Maria";  // Declarația și inițializarea unei variabile de tip text

        System.out.println(nume + " are " + varsta + " ani.");
        // Afișează: "Maria are 25 ani."
    }
}
```

### În concluzie:
Variabilele sunt ca niște **spații temporare de stocare** în care păstrăm date pentru a le folosi în programele noastre. Ele ne ajută să salvăm informații esențiale și să le utilizăm în diferite părți ale codului.
