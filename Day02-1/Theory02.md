În Java, **operatorii** sunt simboluri speciale care efectuează operații pe variabile și valori. Aceștia pot fi folosiți pentru operații matematice, logice, de comparație și altele. În funcție de scopul lor, operatorii din Java sunt împărțiți în mai multe categorii.

### Categorii principale de operatori în Java:

1. **Operatori aritmetici**
2. **Operatori de atribuție**
3. **Operatori de comparație (relaționali)**
4. **Operatori logici**
5. **Operatori unari**
6. **Operatori pe biți**
7. **Operatori ternari**

### 1. Operatorii aritmetici
Aceștia sunt folosiți pentru a efectua operații matematice de bază:

| Operator | Descriere                | Exemplu      |
|----------|--------------------------|--------------|
| `+`      | Adunare                   | `a + b`      |
| `-`      | Scădere                   | `a - b`      |
| `*`      | Înmulțire                 | `a * b`      |
| `/`      | Împărțire                 | `a / b`      |
| `%`      | Modulo (restul împărțirii) | `a % b`      |

**Exemplu:**
```java
int a = 10;
int b = 5;
int suma = a + b;   // suma va fi 15
int rest = a % b;   // rest va fi 0 (deoarece 10 împărțit la 5 nu are rest)
```

### 2. Operatorii de atribuție
Acești operatori sunt folosiți pentru a atribui valori variabilelor.

| Operator | Descriere               | Exemplu      |
|----------|-------------------------|--------------|
| `=`      | Atribuire simplă         | `a = 5`      |
| `+=`     | Adunare și atribuire     | `a += 5`     (echivalent cu `a = a + 5`) |
| `-=`     | Scădere și atribuire     | `a -= 5`     (echivalent cu `a = a - 5`) |
| `*=`     | Înmulțire și atribuire   | `a *= 5`     (echivalent cu `a = a * 5`) |
| `/=`     | Împărțire și atribuire   | `a /= 5`     (echivalent cu `a = a / 5`) |
| `%=`     | Modulo și atribuire      | `a %= 5`     (echivalent cu `a = a % 5`) |

**Exemplu:**
```java
int a = 10;
a += 5;  // a va fi 15 (este echivalent cu a = a + 5)
```

### 3. Operatorii de comparație (relaționali)
Aceștia sunt folosiți pentru a compara două valori și returnează un rezultat de tip `boolean` (adevărat sau fals).

| Operator | Descriere                  | Exemplu  |
|----------|----------------------------|----------|
| `==`     | Egal                        | `a == b` |
| `!=`     | Diferit                     | `a != b` |
| `>`      | Mai mare decât              | `a > b`  |
| `<`      | Mai mic decât               | `a < b`  |
| `>=`     | Mai mare sau egal cu        | `a >= b` |
| `<=`     | Mai mic sau egal cu         | `a <= b` |

**Exemplu:**
```java
int a = 10;
int b = 5;
boolean esteEgal = (a == b);  // false
boolean maiMare = (a > b);    // true
```

### 4. Operatorii logici
Aceștia sunt folosiți pentru a efectua operații logice, în special pentru a combina mai multe condiții.

| Operator | Descriere                | Exemplu     |
|----------|--------------------------|-------------|
| `&&`     | Și logic (AND)            | `a && b`    |
| `||`     | Sau logic (OR)            | `a || b`    |
| `!`      | Negare logică (NOT)       | `!a`        |

**Exemplu:**
```java
boolean x = true;
boolean y = false;
boolean rezultatAnd = x && y;  // false (ambele trebuie să fie true pentru ca rezultatul să fie true)
boolean rezultatOr = x || y;   // true (este suficient ca unul să fie true)
```

### 5. Operatorii unari
Acești operatori operează pe o singură variabilă pentru a o modifica sau a inversa o valoare.

| Operator | Descriere                   | Exemplu      |
|----------|-----------------------------|--------------|
| `++`     | Incrementare (crește cu 1)   | `a++`        |
| `--`     | Decrementare (scade cu 1)    | `a--`        |
| `+`      | Plus (indică o valoare pozitivă) | `+a`        |
| `-`      | Minus (indică o valoare negativă) | `-a`        |
| `!`      | Negare logică               | `!b`         |

**Exemplu:**
```java
int a = 10;
a++;  // a va deveni 11
```

### 6. Operatorii pe biți
Acești operatori operează pe nivel de biți (reprezentarea binară a valorilor).

| Operator | Descriere                   | Exemplu      |
|----------|-----------------------------|--------------|
| `&`      | Și pe biți (bitwise AND)     | `a & b`      |
| `|`      | Sau pe biți (bitwise OR)     | `a | b`      |
| `^`      | Sau exclusiv pe biți (bitwise XOR) | `a ^ b` |
| `~`      | Complement pe biți (negare)  | `~a`         |
| `<<`     | Deplasare la stânga (left shift) | `a << 2` |
| `>>`     | Deplasare la dreapta (right shift) | `a >> 2` |

**Exemplu:**
```java
int a = 5;  // Reprezentare binară: 0101
int b = 3;  // Reprezentare binară: 0011
int c = a & b;  // c va fi 1 (0001)
```

### 7. Operatorul ternar
Este un operator care are trei operanzi și este folosit ca o scurtătură pentru o instrucțiune `if-else`.

| Operator | Descriere                                   | Exemplu                          |
|----------|---------------------------------------------|----------------------------------|
| `?:`     | Condiție ternară (expresie condițională)    | `condiție ? valoare1 : valoare2` |

**Exemplu:**
```java
int a = 10;
int b = 5;
int min = (a < b) ? a : b;  // min va fi 5
```

### Concluzie
Operatorii în Java oferă un mod foarte flexibil și puternic de a manipula date și de a controla fluxul unui program. Fiecare categorie de operatori este esențială pentru diferite tipuri de operații, de la calcule matematice și logice, la compararea valorilor și la operarea cu biți.

Dacă ai întrebări specifice legate de vreun operator sau vrei să vezi exemple mai detaliate, îți pot oferi mai multe informații!
