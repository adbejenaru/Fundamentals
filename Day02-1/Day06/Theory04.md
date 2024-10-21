În Java, există o diferență importantă între utilizarea metodei `.equals()` și operatorul `==` atunci când compari obiecte, inclusiv `String`-uri. Iată o explicație clară:

### 1. **Operatorul `==`:**

- **Comparația referințelor:** Operatorul `==` este folosit pentru a compara **referințele** a două obiecte, adică verifică dacă **cele două variabile indică același obiect în memorie**.
- Dacă două variabile indică același obiect, atunci `==` va returna `true`. Dacă variabilele indică obiecte diferite, chiar dacă conținutul lor este același, `==` va returna `false`.

**Exemplu:**
```java
String s1 = new String("Salut");
String s2 = new String("Salut");

if (s1 == s2) {
    System.out.println("s1 și s2 sunt același obiect.");
} else {
    System.out.println("s1 și s2 sunt obiecte diferite.");
}
```
Acest cod va afișa:
```
s1 și s2 sunt obiecte diferite.
```
Chiar dacă ambele șiruri (`s1` și `s2`) conțin aceeași valoare ("Salut"), ele sunt stocate în locuri diferite în memorie, deci `==` returnează `false`.

### 2. **Metoda `.equals()`:**

- **Comparația conținutului:** Metoda `.equals()` este folosită pentru a compara **conținutul** a două obiecte. În clasa `String`, metoda `.equals()` este suprascrisă pentru a verifica dacă cele două șiruri au aceleași caractere, în aceeași ordine.
- Așadar, `.equals()` compară **valorile** interne ale obiectelor, nu locațiile lor în memorie.

**Exemplu:**
```java
String s1 = new String("Salut");
String s2 = new String("Salut");

if (s1.equals(s2)) {
    System.out.println("s1 și s2 au același conținut.");
} else {
    System.out.println("s1 și s2 au conținut diferit.");
}
```
Acest cod va afișa:
```
s1 și s2 au același conținut.
```
Chiar dacă `s1` și `s2` sunt obiecte diferite în memorie, ele au același conținut, deci `.equals()` returnează `true`.

### Rezumatul diferențelor:

- **`==` compară referințele (locațiile în memorie)**: returnează `true` doar dacă cele două variabile indică exact același obiect.
- **`.equals()` compară conținutul obiectelor**: returnează `true` dacă obiectele au aceleași date (de exemplu, aceleași caractere pentru `String`-uri), chiar dacă sunt obiecte distincte în memorie.

### Exemplu concret:

```java
String s1 = new String("Salut");
String s2 = new String("Salut");

System.out.println(s1 == s2);      // false, pentru că sunt obiecte diferite în memorie
System.out.println(s1.equals(s2)); // true, pentru că au același conținut

String s3 = "Salut";
String s4 = "Salut";

System.out.println(s3 == s4);      // true, pentru că ambele fac parte din "String pool"
System.out.println(s3.equals(s4)); // true, pentru că au același conținut
```

### **String Pool:**

În cazul literalei `String`, cum ar fi `String s3 = "Salut";`, Java folosește un mecanism numit **String pool**, unde literalele identice sunt stocate într-o zonă specială a memoriei. În acest caz, dacă două variabile conțin același literal, ele vor indica exact același obiect din memorie, iar `==` va returna `true`.

Deci, chiar dacă `==` returnează `true` pentru `s3` și `s4`, acest lucru se datorează mecanismului de **String pool**, nu pentru că s-ar compara conținutul direct, ci pentru că ambele variabile referențiază același obiect din pool.

### Concluzie:

- **Folosește `==`** atunci când vrei să verifici dacă două variabile indică exact același obiect.
- **Folosește `.equals()`** atunci când vrei să compari conținutul a două obiecte, cum ar fi șirurile de caractere (`String`-uri).

Pentru a înțelege mai bine cum sunt stocate și gestionate `String`-urile în memorie în Java, este important să separăm două cazuri distincte: utilizarea **literalelor de `String`** și utilizarea **constructorului `new String()`**. Ambele cazuri sunt tratate diferit din punct de vedere al memoriei, iar mecanismul de alocare depinde de **String Pool** și de alocarea normală a obiectelor pe heap.

### 1. **Literalele de tip `String` și String Pool:**

Când declari un `String` literal (de exemplu, `String s = "Salut";`), Java stochează acest `String` în **String Pool**, o zonă specială din memoria heap, destinată optimizării utilizării memoriei pentru `String`-uri.

#### Exemplu:

```java
String s1 = "Salut";  // Literal adăugat în String Pool
String s2 = "Salut";  // Referențiază același obiect din String Pool
```

### **Cum arată în memorie:**

- **String Pool (în memoria Heap):**
  ```
  +------------------+
  |    "Salut"       |  <-- s1 și s2 referențiază acest obiect
  +------------------+
  ```

- **Referințe în Stack (memorie locală pentru fiecare variabilă):**
  ```
  +-------+        +-------+
  |  s1   | -----> | "Salut" (în String Pool)
  +-------+        +-------+
  |  s2   | -----> | "Salut" (în String Pool)
  +-------+        +-------+
  ```

### **Explicație:**
- Când scrii `String s1 = "Salut";`, șirul `"Salut"` este stocat în String Pool, și `s1` referențiază obiectul din String Pool.
- Când scrii `String s2 = "Salut";`, Java detectează că `"Salut"` deja există în String Pool și nu creează un nou obiect, ci doar face ca `s2` să referențieze același obiect.
- Astfel, `s1 == s2` este `true` deoarece ambele variabile referențiază exact același obiect din String Pool.

### 2. **Constructorul `new String()` și alocarea normală pe Heap:**

Când folosești `new String()`, Java **crează întotdeauna un nou obiect** în heap, chiar dacă același `String` există deja în String Pool. Asta înseamnă că vor exista două obiecte diferite, chiar dacă conținutul lor este același.

#### Exemplu:

```java
String s3 = new String("Salut");
String s4 = new String("Salut");
```

### **Cum arată în memorie:**

- **Heap (fără String Pool):**
  ```
  +------------------+       +------------------+
  |   "Salut" (s3)   |       |   "Salut" (s4)   |
  +------------------+       +------------------+
  ```

- **Referințe în Stack (memorie locală pentru fiecare variabilă):**
  ```
  +-------+        +------------------+
  |  s3   | -----> | "Salut" (Heap, nu din Pool)
  +-------+        +------------------+

  +-------+        +------------------+
  |  s4   | -----> | "Salut" (Heap, nu din Pool)
  +-------+        +------------------+
  ```

### **Explicație:**
- Când scrii `String s3 = new String("Salut");`, un **nou obiect** `String` este creat în heap, chiar dacă `"Salut"` există în String Pool.
- Când scrii `String s4 = new String("Salut");`, un **alt obiect** `String` este creat, diferit de `s3`, chiar dacă conținutul este același.
- Astfel, `s3 == s4` va fi `false`, pentru că `s3` și `s4` referențiază obiecte diferite în memorie, chiar dacă conținutul lor este același. Doar **conținutul** poate fi comparat cu `.equals()`, nu referințele.

### Compararea referințelor și a conținutului:

- **Compararea cu `==`**:
  - Compara referințele obiectelor, deci în cazul literalei `String` poate returna `true` (când ambele referințează același obiect în String Pool).
  - În cazul în care folosești `new String()`, compararea va returna `false`, chiar dacă conținutul este identic, deoarece referințele sunt diferite.

- **Compararea cu `.equals()`**:
  - Compară **conținutul** obiectelor, deci atât literalele `String`, cât și cele create cu `new String()` pot returna `true` dacă conținutul este identic.

### Concluzie:

- **Literalele de tip `String`** (cele create direct prin ghilimele) sunt stocate în **String Pool** și reutilizate, ceea ce face ca referințele să fie aceleași dacă conținutul este identic.
- **Obiectele create cu `new String()`** nu sunt adăugate automat în String Pool și sunt stocate în heap-ul normal, ceea ce înseamnă că referențele lor sunt diferite, chiar dacă conținutul este același.
