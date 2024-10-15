### Buclă (Loop) în Java

**Bucle** (sau **loops**) sunt structuri de control folosite pentru a repeta o secțiune de cod de mai multe ori, până când o anumită condiție este îndeplinită. Ele sunt utile când dorim să executăm aceleași instrucțiuni în mod repetat, fără a le scrie de mai multe ori.

În Java, există patru tipuri principale de bucle:
1. **`for`**
2. **`while`**
3. **`do-while`**
4. **`for-each`** (folosit pentru a itera prin colecții sau array-uri)

### 1. **Bucla `for`**

Bucla `for` este utilizată atunci când știi dinainte de câte ori dorești să repeți o secțiune de cod. Se compune din trei părți:
- Inițializarea variabilei de control.
- Condiția care verifică dacă bucla trebuie să continue.
- Incrementează sau decrementează variabila de control.

#### Sintaxă:

```java
for (initializare; conditie; incrementare/decrementare) {
    // cod care se execută în buclă
}
```

#### Exemplu:

```java
public class ForLoopExample {
    public static void main(String[] args) {
        // Bucla for care numără de la 1 la 5
        for (int i = 1; i <= 5; i++) {
            System.out.println("i = " + i);
        }
    }
}
```

#### Explicație:
- **`int i = 1`**: Inițializarea. Variabila `i` este inițializată cu valoarea 1.
- **`i <= 5`**: Condiția de continuare a buclei. Bucla se repetă atât timp cât `i` este mai mic sau egal cu 5.
- **`i++`**: Incrementează valoarea lui `i` după fiecare iterație.

### 2. **Bucla `while`**

Bucla `while` repetă o secțiune de cod atâta timp cât condiția specificată este adevărată. Se folosește când nu știi dinainte de câte ori se va repeta bucla, ci doar când se va opri (pe baza condiției).

#### Sintaxă:

```java
while (conditie) {
    // cod care se execută în buclă
}
```

#### Exemplu:

```java
public class WhileLoopExample {
    public static void main(String[] args) {
        int i = 1;
        
        // Bucla while care se repetă atâta timp cât i este mai mic sau egal cu 5
        while (i <= 5) {
            System.out.println("i = " + i);
            i++;  // Incrementarea variabilei pentru a evita o buclă infinită
        }
    }
}
```

#### Explicație:
- **`i <= 5`**: Condiția buclei. Atâta timp cât `i` este mai mic sau egal cu 5, bucla se va repeta.
- **`i++`**: După fiecare iterație, valoarea lui `i` este incrementată pentru a apropia bucla de finalizare.

### 3. **Bucla `do-while`**

Bucla `do-while` este similară cu bucla `while`, dar diferența principală este că secțiunea de cod din buclă se execută **cel puțin o dată**, chiar dacă condiția este falsă de la început.

#### Sintaxă:

```java
do {
    // cod care se execută în buclă
} while (conditie);
```

#### Exemplu:

```java
public class DoWhileLoopExample {
    public static void main(String[] args) {
        int i = 1;
        
        // Bucla do-while care se execută cel puțin o dată
        do {
            System.out.println("i = " + i);
            i++;
        } while (i <= 5);
    }
}
```

#### Explicație:
- În bucla `do-while`, codul din buclă se execută cel puțin o dată, chiar dacă condiția este falsă, deoarece condiția este evaluată **după** executarea codului.
- **`while (i <= 5)`**: Bucla se repetă atâta timp cât `i` este mai mic sau egal cu 5.

### 4. **Bucla `for-each`**

Bucla `for-each` este utilizată pentru a itera prin colecții (cum ar fi array-uri, liste) și este utilă atunci când nu ai nevoie să controlezi indexul. Este o formă simplificată a buclei `for`.

#### Sintaxă:

```java
for (tip variabila : colectie) {
    // cod care se execută în buclă
}
```

#### Exemplu:

```java
public class ForEachLoopExample {
    public static void main(String[] args) {
        int[] numere = {1, 2, 3, 4, 5};
        
        // Bucla for-each care iterează printr-un array
        for (int numar : numere) {
            System.out.println("Număr: " + numar);
        }
    }
}
```

#### Explicație:
- **`for (int numar : numere)`**: Bucla iterează prin fiecare element din array-ul `numere` și stochează valoarea curentă în variabila `numar`.

---

### Controlul buclelor: `break` și `continue`

#### **`break`**
- `break` este folosit pentru a **întrerupe** bucla imediat, chiar dacă condiția de continuare este încă adevărată.
- Este util când vrei să oprești bucla înainte ca aceasta să termine în mod natural.

#### Exemplu cu `break`:

```java
public class BreakExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            if (i == 3) {
                break;  // Oprește bucla când i este 3
            }
            System.out.println("i = " + i);
        }
    }
}
```

#### **`continue`**
- `continue` este folosit pentru a **sări** peste restul codului din buclă pentru iterația curentă și a trece direct la următoarea iterație.

#### Exemplu cu `continue`:

```java
public class ContinueExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            if (i == 3) {
                continue;  // Sare peste iterația când i este 3
            }
            System.out.println("i = " + i);
        }
    }
}
```

---

### Diferențe între tipurile de bucle:

- **`for`** este ideal atunci când știi de câte ori vrei să repeți o acțiune.
- **`while`** este util când vrei să repeți o acțiune atâta timp cât o condiție este adevărată și nu știi dinainte câte iterații vor fi.
- **`do-while`** este asemănător cu `while`, dar se execută cel puțin o dată, chiar dacă condiția este falsă.
- **`for-each`** este foarte util atunci când lucrezi cu colecții de date și vrei să parcurgi fiecare element.

### Concluzie:
Buclele sunt esențiale în Java pentru a repeta secțiuni de cod și pentru a automatiza sarcinile repetitive. Alegerea buclei potrivite depinde de problema pe care o rezolvi și de modul în care trebuie să controlezi numărul de iterații.
