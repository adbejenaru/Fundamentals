Pentru a evita utilizarea `nested if` (instrucțiuni `if` imbricate), poți folosi diverse strategii, precum:

1. **Combinarea condițiilor cu operatori logici** (`&&`, `||`).
2. **Returnarea timpurie** în metode (cunoscută ca "early return").
3. **Refactorizarea condițiilor complexe în metode separate**.
4. **Utilizarea blocurilor `else if`** pentru a organiza mai bine condițiile.

Mai jos sunt câteva exemple care oferă alternative la `nested if`.

---

### 1. **Combinarea condițiilor cu operatorul `&&` (AND)**

În loc să scrii un `if` imbricat, poți combina mai multe condiții folosind operatorul logic `&&`, astfel încât toate condițiile să fie evaluate simultan. Această abordare simplifică structura și face codul mai ușor de citit.

#### Exemplu fără `nested if`:
```java
public class NoNestedIfExample {
    public static void main(String[] args) {
        int varsta = 20;
        boolean arePermis = true;
        boolean masinaFunctionala = true;

        // Verificăm toate condițiile în același `if` folosind operatorul AND (&&)
        if (varsta >= 18 && arePermis && masinaFunctionala) {
            System.out.println("Poți pleca la drum.");
        } else if (varsta < 18) {
            System.out.println("Nu ești suficient de mare pentru a conduce.");
        } else if (!arePermis) {
            System.out.println("Ai nevoie de permis pentru a conduce.");
        } else {
            System.out.println("Mașina nu funcționează.");
        }
    }
}
```

### Explicație:
- Toate condițiile (`varsta >= 18`, `arePermis`, `masinaFunctionala`) sunt evaluate simultan în aceeași instrucțiune `if`.
- Dacă toate sunt adevărate, se afișează mesajul că persoana poate pleca la drum.
- În caz contrar, se tratează fiecare posibilă situație în blocurile `else if`.

---

### 2. **Returnare timpurie (Early Return)**

Dacă scrii o metodă și vrei să eviți `nested if`, poți folosi `return` pentru a ieși din metodă imediat ce o condiție este falsă. Astfel, codul devine mai clar și nu mai trebuie să te complici cu multe blocuri de cod imbricate.

#### Exemplu cu returnare timpurie:
```java
public class EarlyReturnExample {

    public static void verificaConducere(int varsta, boolean arePermis, boolean masinaFunctionala) {
        if (varsta < 18) {
            System.out.println("Nu ești suficient de mare pentru a conduce.");
            return; // Ieșim din metodă
        }

        if (!arePermis) {
            System.out.println("Ai nevoie de permis pentru a conduce.");
            return; // Ieșim din metodă
        }

        if (!masinaFunctionala) {
            System.out.println("Mașina nu funcționează.");
            return; // Ieșim din metodă
        }

        // Dacă toate condițiile sunt îndeplinite, continuăm
        System.out.println("Poți pleca la drum.");
    }

    public static void main(String[] args) {
        verificaConducere(20, true, true);  // Poți pleca la drum.
        verificaConducere(16, true, true);  // Nu ești suficient de mare pentru a conduce.
        verificaConducere(20, false, true); // Ai nevoie de permis pentru a conduce.
    }
}
```

### Explicație:
- Folosim `return` pentru a ieși din metodă imediat ce o condiție este falsă.
- Acest lucru elimină necesitatea `else`-urilor și face codul mai simplu și mai curat.

---

### 3. **Mutarea logicii în metode separate**

Dacă ai condiții complexe și ai nevoie de claritate, poți muta fiecare verificare într-o metodă separată, care să returneze un `boolean`. Apoi, poți combina rezultatele acestor metode.

#### Exemplu cu metode separate:
```java
public class SeparateMethodsExample {

    public static boolean esteMajor(int varsta) {
        return varsta >= 18;
    }

    public static boolean arePermis(boolean arePermis) {
        return arePermis;
    }

    public static boolean esteMasinaFunctionala(boolean masinaFunctionala) {
        return masinaFunctionala;
    }

    public static void main(String[] args) {
        int varsta = 20;
        boolean permis = true;
        boolean masina = true;

        if (esteMajor(varsta) && arePermis(permis) && esteMasinaFunctionala(masina)) {
            System.out.println("Poți pleca la drum.");
        } else {
            System.out.println("Nu poți pleca la drum.");
        }
    }
}
```

### Explicație:
- Am mutat fiecare verificare într-o metodă separată (`esteMajor()`, `arePermis()` și `esteMasinaFunctionala()`).
- Apoi, toate aceste metode sunt apelate într-un singur `if` pentru a decide dacă persoana poate pleca la drum.

---

### 4. **Utilizarea `else if`**

Poți folosi `else if` pentru a trata cazuri diferite, fără a imbrica mai multe `if`-uri.

#### Exemplu cu `else if`:
```java
public class ElseIfExample {
    public static void main(String[] args) {
        int varsta = 20;
        boolean arePermis = false;
        boolean masinaFunctionala = true;

        if (varsta < 18) {
            System.out.println("Nu ești suficient de mare pentru a conduce.");
        } else if (!arePermis) {
            System.out.println("Ai nevoie de permis pentru a conduce.");
        } else if (!masinaFunctionala) {
            System.out.println("Mașina nu funcționează.");
        } else {
            System.out.println("Poți pleca la drum.");
        }
    }
}
```

### Explicație:
- Fiecare condiție este tratată în cadrul unui bloc separat `else if`.
- Această abordare evită imbricarea `if`-urilor și face ca fiecare condiție să fie clară și gestionată independent.

---

### Concluzie:
Folosirea alternativelor la `nested if` ajută la menținerea codului mai clar, mai ușor de înțeles și mai ușor de întreținut. Printre soluțiile alternative, cele mai comune sunt:
1. **Combinarea condițiilor** cu operatori logici.
2. **Returnarea timpurie** din metode pentru a evita blocuri suplimentare de cod.
3. **Refactorizarea condițiilor în metode separate**.
4. **Utilizarea `else if`** pentru a trata mai multe cazuri în locul imbricării.
