În Java, bucla `for` are mai multe variante pentru a se potrivi diferitelor situații. Iată o listă a tipurilor de bucle `for` disponibile:

---

### 1. **Bucla `for` clasică**

Aceasta este structura tradițională a buclei `for`, utilizată în principal când numărul de iterații este cunoscut.

#### Structură:
```java
for (initializare; conditie; incrementare) {
    // Codul care se execută la fiecare iterație
}
```

#### Exemplu:
```java
for (int i = 0; i < 5; i++) {
    System.out.println("Valoarea lui i: " + i);
}
```

**Explicație**:
- `initializare`: stabilește valoarea inițială a variabilei de control (ex: `int i = 0;`).
- `conditie`: este evaluată înainte de fiecare iterație; bucla rulează cât timp condiția este `true`.
- `incrementare`: definește modul în care variabila de control este modificată după fiecare iterație.

---

### 2. **Bucla `for` cu mai multe variabile**

În bucla `for`, poți inițializa și controla mai multe variabile în același timp.

#### Exemplu:
```java
for (int i = 0, j = 10; i < j; i++, j--) {
    System.out.println("i: " + i + ", j: " + j);
}
```

**Explicație**: În acest exemplu, `i` crește la fiecare iterație, iar `j` scade. Bucla se oprește când `i` devine egal cu `j`.

---

### 3. **Bucla `for` fără condiții specifice**

În Java, toate cele trei părți ale buclei `for` sunt opționale. Poți crea o buclă infinită omisiunea tuturor celor trei componente.

#### Exemplu:
```java
for (;;) {
    System.out.println("Buclă infinită");
    break; // Adăugăm `break` pentru a evita bucla infinită
}
```

**Explicație**: Dacă omitem condiția, bucla `for` va rula la nesfârșit (buclă infinită) până când este întreruptă explicit (de exemplu, cu `break`).

---

### 4. **Enhanced `for` (sau "for-each")**

Aceasta este o versiune simplificată a buclei `for`, numită și `for-each`, utilizată pentru a itera peste colecții și array-uri fără a folosi un contor.

#### Structură:
```java
for (Tip element : colectie) {
    // Codul care se execută pentru fiecare element din colecție
}
```

#### Exemplu:
```java
int[] numere = {1, 2, 3, 4, 5};
for (int numar : numere) {
    System.out.println("Numărul este: " + numar);
}
```

**Explicație**: Această buclă este utilă pentru array-uri și colecții (`List`, `Set`, etc.). Automatizează procesul de iterare și este mai ușor de citit. Nu poți modifica direct indexul elementului curent.

---

### 5. **Bucla `for` în stil funcțional (Java 8 și versiuni ulterioare)**

Începând cu Java 8, poți folosi metode funcționale, cum ar fi `forEach`, pentru a itera prin colecții, lucru util în special în contextul expresiilor lambda.

#### Exemplu:
```java
List<String> nume = Arrays.asList("Ana", "Maria", "Ion");
nume.forEach(numeCurent -> System.out.println("Nume: " + numeCurent));
```

**Explicație**: `forEach` folosește o expresie lambda (`numeCurent -> System.out.println(...)`), oferind un mod concis și funcțional de a itera printr-o colecție.

---

### 6. **Bucla `for` cu `break` și `continue`**

Aceste cuvinte cheie pot fi folosite în bucla `for` pentru a controla fluxul execuției.

- **`break`**: Oprește complet execuția buclei.
- **`continue`**: Sare la următoarea iterație a buclei, ignorând codul de după `continue` în iterația curentă.

#### Exemplu:
```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        continue; // Sare peste restul codului și trece la următoarea iterație
    }
    if (i == 8) {
        break; // Oprește bucla complet
    }
    System.out.println("Valoarea lui i: " + i);
}
```

**Explicație**: `continue` sare peste iterația curentă (de exemplu, când `i == 5`), iar `break` oprește complet bucla (când `i == 8`).

---

Aceste tipuri de bucle `for` oferă flexibilitate în Java pentru a se adapta la diferite nevoi de programare și scenarii de iterație.


În Java, există două tipuri principale de bucle `while`: **bucla `while` simplă** și **bucla `do-while`**. În afară de aceste două, putem folosi câteva tehnici pentru a obține comportamente variate în funcție de necesități, dar toate se bazează pe structura de bază a buclelor `while`.

### 1. **Bucla `while` simplă**

Aceasta este bucla `while` clasică, care verifică o condiție înainte de a executa codul din buclă. Dacă condiția este `true`, bucla va continua să ruleze. Dacă este `false` de la început, codul din buclă nu se va executa deloc.

#### Structură:
```java
while (conditie) {
    // Codul care se execută cât timp condiția este adevărată
}
```

#### Exemplu:
```java
int i = 1;
while (i <= 5) {
    System.out.println("Valoarea lui i: " + i);
    i++;
}
```

**Explicație**: Bucla va afișa valorile lui `i` de la 1 la 5, deoarece se oprește când `i` devine mai mare decât 5.

### 2. **Bucla `do-while`**

Bucla `do-while` este o variantă a `while` care se execută **cel puțin o dată**, deoarece condiția este verificată la finalul fiecărei iterații.

#### Structură:
```java
do {
    // Codul care se execută cel puțin o dată
} while (conditie);
```

#### Exemplu:
```java
int j = 1;
do {
    System.out.println("Valoarea lui j: " + j);
    j++;
} while (j <= 5);
```

**Explicație**: În acest exemplu, valoarea lui `j` va fi afișată de la 1 la 5. Chiar dacă `j` ar fi avut o valoare mai mare de 5 de la început, codul s-ar executa cel puțin o dată înainte de a verifica condiția.

---

### Alte tehnici și tipuri de comportamente în bucle `while`

Deși Java nu are alte tipuri de `while`, poți folosi câteva tehnici suplimentare pentru a obține diferite comportamente:

1. **Bucla `while` infinită**: O buclă `while` care rulează la nesfârșit, folosind o condiție care este întotdeauna `true`.
   ```java
   while (true) {
       System.out.println("Aceasta este o buclă infinită");
       // Trebuie să folosești `break` pentru a ieși din buclă la un moment dat
       if (conditieDeOprire) {
           break;
       }
   }
   ```

2. **Bucla `while` cu `break`**: `break` permite ieșirea din buclă înainte ca aceasta să ajungă la condiția sa naturală de oprire. Aceasta este utilă pentru a termina bucla în funcție de o anumită condiție internă.
   ```java
   int k = 0;
   while (k < 10) {
       if (k == 5) {
           break; // Oprește bucla când k este 5
       }
       System.out.println("Valoarea lui k: " + k);
       k++;
   }
   ```

3. **Bucla `while` cu `continue`**: `continue` permite sări peste restul codului din buclă și trecerea direct la următoarea iterație.
   ```java
   int m = 0;
   while (m < 10) {
       m++;
       if (m % 2 == 0) {
           continue; // Sari peste afișare pentru valorile pare
       }
       System.out.println("Valoarea lui m: " + m); // Afișează doar valorile impare
   }
   ```

4. **Bucla `while` imbricată (Nested `while`)**: Bucla `while` poate fi folosită în interiorul altei bucle `while`. Aceasta este utilă pentru lucrul cu structuri de date multidimensionale sau pentru efectuarea de iterații complexe.
   ```java
   int i = 1;
   while (i <= 3) {
       int j = 1;
       while (j <= 3) {
           System.out.println("i: " + i + ", j: " + j);
           j++;
       }
       i++;
   }
   ```

**Explicație**: În acest exemplu, pentru fiecare valoare a lui `i` de la 1 la 3, bucla internă `while` va itera `j` de la 1 la 3, rezultând astfel într-o structură de tip matrice.

---

### Rezumat

- **`while` simplu**: Rulează cât timp condiția este `true`.
- **`do-while`**: Rulează cel puțin o dată, deoarece condiția este verificată la sfârșitul buclei.
- **Bucle `while` infinite, cu `break` sau `continue`**: Permite un control suplimentar asupra execuției buclei.
- **Bucle `while` imbricate**: Folosite pentru structuri complexe sau iterare multidimensională.

Acestea sunt toate tipurile și tehnicile `while` pe care le poți folosi pentru a manipula fluxul execuției în Java.
