### Regular Expressions (Expresii Regulate) - Introducere în Java

Expresiile regulate, cunoscute și sub numele de **regex**, reprezintă șabloane folosite pentru a verifica dacă un șir de caractere respectă un anumit format. În Java, acestea sunt utile pentru a valida datele introduse de utilizatori, precum verificarea dacă o adresă de email este corectă sau dacă un număr de telefon are formatul potrivit.

#### Ce sunt expresiile regulate?

Expresiile regulate sunt modele formate din secvențe de caractere sau simboluri speciale, care descriu structura unui șir de caractere. Ele sunt utile pentru:
- Căutare și potrivire de șiruri de caractere.
- Validarea formatului unor date (de exemplu, email, coduri poștale, parole).
- Înlocuirea sau modificarea anumitor secvențe dintr-un șir.

Exemplu simplu de expresie regulată pentru validarea unui nume:
```regex
"[A-Z][a-z]+"
```
Aceasta verifică dacă un nume începe cu o literă mare (`[A-Z]`), urmată de una sau mai multe litere mici (`[a-z]+`).

---

### Structura expresiilor regulate

Expresiile regulate constau dintr-o secvență de **atomi**:
- **Atom**: Elementul de bază al unei expresii regulate. Acesta poate fi:
  - O literă (`a`, `b`, etc.).
  - Un număr (`1`, `2`, etc.).
  - Un caracter special (`@`, `!`, etc.).
  
Atomi pot fi combinați pentru a forma grupuri sau secvențe, iar aceste grupuri pot fi restricționate cu **quantifiers** (quantificatori) care specifică de câte ori trebuie să apară atomul.

---

### Quantificatori (Quantifiers)

**Quantificatorii** descriu numărul de repetări al unui atom sau secvență într-un șir de caractere. De exemplu:
- `a+bcde`: Litera `a` trebuie să apară cel puțin o dată, urmată de secvența „bcde”.
  
Cele mai comune quantificatoare sunt:
- **`+`**: Apare de **cel puțin o dată**.
- **`*`**: Apare de **zero sau mai multe ori**.
- **`?`**: Apare de **zero sau o dată**.
- **`{n}`**: Apare exact de **n ori**.
- **`{n,m}`**: Apare de **cel puțin n și cel mult m ori**.

Exemplu:
```regex
a+bcde
```
Acest șablon caută un șir care începe cu una sau mai multe litere „a”, urmată de secvența „bcde”.

---

### Ranges (Intervale) și Groups (Grupuri)

**Intervalele** și **grupurile** sunt alte instrumente utile în expresiile regulate.

1. **Intervale**:
   - Permit definirea unui set de caractere care sunt permise într-o poziție anume.
   - Se definesc între paranteze pătrate: `[ ]`.
   - Pot include fie o listă de caractere (de exemplu, `[abc]`), fie un interval de caractere (de exemplu, `[a-z]`).

   Exemple:
   - **`[0-9]`**: Un singur caracter care este o cifră.
   - **`[a-z]`**: O literă mică.
   - **`[A-Z]`**: O literă mare.

2. **Grupuri**:
   - Caracterele pot fi grupate între paranteze rotunde: `( )`.
   - Grupurile sunt utile pentru a aplica quantificatori sau pentru a capta subșiruri din șirul original.

Exemple de intervale în expresii regulate:
- `[0-9]`: Orice cifră între 0 și 9.
- `[a-z]`: Orice literă mică.
- `[A-Z]`: Orice literă mare.

---

### Implementarea expresiilor regulate în Java

În Java, expresiile regulate sunt utilizate cu ajutorul claselor **Pattern** și **Matcher**, ambele din pachetul `java.util.regex`.

1. **Pattern**:
   - **Pattern** este o clasă care reprezintă o expresie regulată compilată.
   - Folosim metoda statică `compile()` pentru a crea un obiect `Pattern` pe baza unui șir care reprezintă o expresie regulată.

   Exemplu:
   ```java
   Pattern pattern = Pattern.compile("a+bcd");
   ```

2. **Matcher**:
   - **Matcher** este o clasă care verifică dacă un șir se potrivește cu un `Pattern`.
   - Metoda `matcher()` a clasei `Pattern` returnează un obiect `Matcher` care poate fi folosit pentru a verifica potrivirile într-un șir.
   - Metode importante din clasa `Matcher`:
     - **matches()**: Verifică dacă șirul întreg se potrivește cu expresia regulată.
     - **find()**: Caută dacă există vreo secvență în șirul de caractere care se potrivește cu expresia regulată.

   Exemplu:
   ```java
   Pattern pattern = Pattern.compile("a+bcd");
   Matcher matcher = pattern.matcher("aaaaabcd aaaaaaabbcd");
   matcher.matches();  // returnează true/false
   ```

   De asemenea, **`find()`** este util pentru a căuta secvențe în șiruri lungi:
   ```java
   matcher.find();  // returnează true/false
   ```

---

### Recapitulare

- **Expresiile regulate** sunt modele care ajută la identificarea formatului unui șir de caractere.
- **Quantificatorii** determină de câte ori trebuie să apară un atom sau un grup.
- **Intervalele** sunt folosite pentru a specifica un set de caractere posibile într-o poziție anume.
- În Java, folosim clasele **Pattern** și **Matcher** pentru a lucra cu expresii regulate. 

Expresiile regulate sunt extrem de utile în situații precum validarea formatului datelor, căutarea de pattern-uri în text sau înlocuirea unor secvențe într-un șir.

Sigur! Iată câteva exemple simple și ușor de înțeles despre cum să folosești expresiile regulate în Java. Fiecare exemplu va ilustra o situație comună și cum se poate rezolva folosind regex.

---

### 1. **Validarea unui număr de telefon simplu**
Acest exemplu validează dacă un număr de telefon este format din exact 10 cifre.

```java
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class PhoneValidation {
    public static void main(String[] args) {
        String phoneNumber = "0745123456";  // Număr de telefon format din 10 cifre
        
        // Expresia regulată: exact 10 cifre
        String regex = "\\d{10}";
        
        Pattern pattern = Pattern.compile(regex);
        Matcher matcher = pattern.matcher(phoneNumber);
        
        if (matcher.matches()) {
            System.out.println("Număr de telefon valid!");
        } else {
            System.out.println("Număr de telefon invalid!");
        }
    }
}
```

**Explicație:**
- **`\\d{10}`**: `\\d` înseamnă o cifră, iar `{10}` înseamnă că trebuie să fie exact 10 cifre.

---

### 2. **Verificarea unui șir care conține doar litere mari**
Acest exemplu verifică dacă un șir de caractere conține doar litere mari.

```java
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class UppercaseValidation {
    public static void main(String[] args) {
        String text = "HELLO";  // Șir format doar din litere mari
        
        // Expresie regulată: doar litere mari
        String regex = "^[A-Z]+$";
        
        Pattern pattern = Pattern.compile(regex);
        Matcher matcher = pattern.matcher(text);
        
        if (matcher.matches()) {
            System.out.println("Textul conține doar litere mari!");
        } else {
            System.out.println("Textul NU conține doar litere mari!");
        }
    }
}
```

**Explicație:**
- **`^[A-Z]+$`**: `^[A-Z]+$` verifică dacă șirul începe și se termină cu litere mari (`A-Z`), iar `+` înseamnă că trebuie să fie una sau mai multe litere mari.

---

### 3. **Înlocuirea tuturor cifrelor dintr-un text cu `#`**
Acest exemplu înlocuiește toate cifrele dintr-un text cu caracterul `#`.

```java
public class ReplaceNumbers {
    public static void main(String[] args) {
        String text = "Salut, am 3 câini și 2 pisici.";  // Textul care conține cifre
        
        // Înlocuim toate cifrele cu #
        String rezultat = text.replaceAll("\\d", "#");
        System.out.println("Text modificat: " + rezultat);
    }
}
```

**Explicație:**
- **`\\d`**: Reprezintă orice cifră. `replaceAll()` înlocuiește toate cifrele din text cu caracterul `#`.

---

### 4. **Extrage doar literele dintr-un șir mixt**
Acest exemplu extrage doar literele dintr-un șir care conține atât litere, cât și cifre.

```java
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class ExtractLetters {
    public static void main(String[] args) {
        String text = "a1b2c3d4e5f6";  // Șir mixt cu litere și cifre
        
        // Expresie regulată pentru extragerea literelor
        String regex = "[a-zA-Z]";
        
        Pattern pattern = Pattern.compile(regex);
        Matcher matcher = pattern.matcher(text);
        
        System.out.print("Litere găsite: ");
        while (matcher.find()) {
            System.out.print(matcher.group());
        }
    }
}
```

**Explicație:**
- **`[a-zA-Z]`**: Găsește orice literă mică (`a-z`) sau literă mare (`A-Z`).
- **`matcher.find()`**: Caută toate potrivirile în șirul text.

---

### 5. **Validarea unei adrese de email**
Acest exemplu verifică dacă o adresă de email are un format simplu valid.

```java
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class EmailValidation {
    public static void main(String[] args) {
        String email = "exemplu@domeniu.com";
        
        // Expresie regulată pentru email
        String regex = "^[A-Za-z0-9+_.-]+@[A-Za-z0-9.-]+$";
        
        Pattern pattern = Pattern.compile(regex);
        Matcher matcher = pattern.matcher(email);
        
        if (matcher.matches()) {
            System.out.println("Email valid!");
        } else {
            System.out.println("Email invalid!");
        }
    }
}
```

**Explicație:**
- **`^[A-Za-z0-9+_.-]+@[A-Za-z0-9.-]+$`**: Aceasta este o expresie regulată simplă pentru validarea adreselor de email. Permite litere, cifre, caractere speciale precum `+`, `_`, `.` sau `-`, urmate de simbolul `@` și domeniu.

---

### 6. **Verificarea unui cod poștal simplu de 5 cifre**
Acest exemplu validează un cod poștal format din 5 cifre.

```java
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class PostalCodeValidation {
    public static void main(String[] args) {
        String postalCode = "12345";  // Cod poștal valid
        
        // Expresie regulată pentru cod poștal de 5 cifre
        String regex = "\\d{5}";
        
        Pattern pattern = Pattern.compile(regex);
        Matcher matcher = pattern.matcher(postalCode);
        
        if (matcher.matches()) {
            System.out.println("Cod poștal valid!");
        } else {
            System.out.println("Cod poștal invalid!");
        }
    }
}
```

**Explicație:**
- **`\\d{5}`**: Reprezintă exact 5 cifre consecutive.

---

### 7. **Separarea unui șir de caractere pe baza unui separator (virgulă)**
Acest exemplu împarte un șir de cuvinte separate prin virgulă într-un array de string-uri.

```java
public class SplitStringExample {
    public static void main(String[] args) {
        String text = "mere, pere, prune, portocale";
        
        // Folosim expresia regulată pentru a despărți textul la fiecare virgulă
        String[] fructe = text.split(",\\s*");
        
        for (String fruct : fructe) {
            System.out.println(fruct);
        }
    }
}
```

**Explicație:**
- **`,\\s*`**: Desparte șirul la fiecare virgulă, ignorând spațiile din jurul ei. `\\s*` înseamnă „zero sau mai multe spații albe”.

---

Aceste exemple acoperă situații comune și sunt destul de ușoare pentru a înțelege cum funcționează expresiile regulate în Java. Ele te pot ajuta să validezi date, să cauți și să modifici șiruri de caractere într-un mod eficient.
