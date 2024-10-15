În Java, există mai multe modalități de a combina instrucțiunile `if` pentru a gestiona diferite cazuri și condiții. Mai jos sunt câteva exemple comune pentru a arăta cum putem extinde și combina blocurile `if`.

### 1. **`if-else` standard**
Acesta este cazul de bază, unde există o condiție și două căi: una pentru când condiția este adevărată și alta pentru când este falsă.

#### Exemplu:
```java
public class IfElseExample {
    public static void main(String[] args) {
        int varsta = 20;

        if (varsta >= 18) {
            System.out.println("Ești major.");
        } else {
            System.out.println("Nu ești major.");
        }
    }
}
```

### 2. **`if-else if-else` (ramuri multiple)**
Aceasta este o variantă extinsă în care ai mai multe condiții posibile. Dacă o condiție este adevărată, blocul respectiv va fi executat și celelalte ramuri vor fi ignorate.

#### Exemplu:
```java
public class IfElseIfExample {
    public static void main(String[] args) {
        int nota = 85;

        if (nota >= 90) {
            System.out.println("Ai primit nota A.");
        } else if (nota >= 80) {
            System.out.println("Ai primit nota B.");
        } else if (nota >= 70) {
            System.out.println("Ai primit nota C.");
        } else {
            System.out.println("Ai primit nota D.");
        }
    }
}
```

### 3. **`if` fără `else`**
Poți folosi doar instrucțiunea `if`, fără blocul `else`, atunci când vrei să execuți un bloc de cod doar dacă condiția este adevărată. Dacă nu este, programul va continua fără să facă nimic în mod specific pentru ramura falsă.

#### Exemplu:
```java
public class IfWithoutElse {
    public static void main(String[] args) {
        int varsta = 18;

        if (varsta >= 18) {
            System.out.println("Ești major.");
        }
        // Nu există else, programul continuă direct
        System.out.println("Programul continuă...");
    }
}
```

### 4. **Combinarea mai multor condiții (`&&` și `||`)**
Instrucțiunile `if` pot folosi operatori logici precum **`&&`** (și) și **`||`** (sau) pentru a combina mai multe condiții.

#### Exemplu cu `&&` (AND - ambele condiții trebuie să fie adevărate):
```java
public class IfAndOperator {
    public static void main(String[] args) {
        int varsta = 25;
        boolean arePermis = true;

        if (varsta >= 18 && arePermis) {
            System.out.println("Poți conduce o mașină.");
        } else {
            System.out.println("Nu poți conduce o mașină.");
        }
    }
}
```

#### Exemplu cu `||` (OR - una dintre condiții trebuie să fie adevărată):
```java
public class IfOrOperator {
    public static void main(String[] args) {
        int varsta = 17;
        boolean arePermisSpecial = true;

        if (varsta >= 18 || arePermisSpecial) {
            System.out.println("Poți conduce o mașină.");
        } else {
            System.out.println("Nu poți conduce o mașină.");
        }
    }
}
```

### 5. **`if` imbricat (nested if)**
Un `if` poate fi inclus în interiorul altui `if`, caz în care evaluarea este mai complexă și depinde de rezultatul ambelor condiții.

#### Exemplu:
```java
public class NestedIfExample {
    public static void main(String[] args) {
        int varsta = 20;
        boolean arePermis = true;

        if (varsta >= 18) {
            if (arePermis) {
                System.out.println("Poți conduce o mașină.");
            } else {
                System.out.println("Ai nevoie de permis pentru a conduce.");
            }
        } else {
            System.out.println("Nu ești suficient de mare pentru a conduce.");
        }
    }
}
```

### 6. **Ternary Operator (`? :`)**
Operatorul ternar este o versiune concisă a unei instrucțiuni `if-else`, folosită pentru expresii simple.

#### Exemplu:
```java
public class TernaryExample {
    public static void main(String[] args) {
        int varsta = 18;

        String mesaj = (varsta >= 18) ? "Ești major." : "Nu ești major.";
        System.out.println(mesaj);
    }
}
```

### 7. **Switch vs. `if-else`**
Când ai mai multe cazuri posibile pentru o singură variabilă, poți folosi `switch` în loc de un lanț lung de `if-else`. Totuși, `if-else` este mai flexibil, deoarece permite compararea unor condiții mai complexe.

#### Exemplu:
```java
public class SwitchExample {
    public static void main(String[] args) {
        int ziuaSaptamanii = 3;

        switch (ziuaSaptamanii) {
            case 1:
                System.out.println("Luni");
                break;
            case 2:
                System.out.println("Marți");
                break;
            case 3:
                System.out.println("Miercuri");
                break;
            default:
                System.out.println("Altă zi a săptămânii.");
        }
    }
}
```

### Concluzie:
Poți combina instrucțiuni `if` în diverse moduri, în funcție de cerințele aplicației. `if-else`, `else if`, combinarea condițiilor cu `&&` și `||`, utilizarea operatorului ternar, și instrucțiuni `if` imbricate oferă multă flexibilitate și putere de control în fluxul programului.
