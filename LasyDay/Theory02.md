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
