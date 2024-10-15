Desigur! Iată mai multe exemple de instrucțiuni condiționale în Java, explicate detaliat:

### 1. **Exemplu simplu cu `if`**

```java
int temperatură = 30;

if (temperatură > 25) {
    System.out.println("Este cald afară.");
}
```
Aici, mesajul "Este cald afară" va fi afișat doar dacă temperatura este mai mare de 25.

---

### 2. **Exemplu cu `if-else`**

```java
int oreDormite = 6;

if (oreDormite >= 8) {
    System.out.println("Ai dormit suficient.");
} else {
    System.out.println("Nu ai dormit suficient.");
}
```
Dacă valoarea variabilei `oreDormite` este mai mică de 8, va afișa "Nu ai dormit suficient."

---

### 3. **Exemplu cu `if-else if-else`**

```java
int punctaj = 75;

if (punctaj >= 90) {
    System.out.println("Ai primit nota A.");
} else if (punctaj >= 80) {
    System.out.println("Ai primit nota B.");
} else if (punctaj >= 70) {
    System.out.println("Ai primit nota C.");
} else {
    System.out.println("Ai primit nota D.");
}
```
În acest exemplu, programul verifică mai multe condiții și atribuie o notă în funcție de punctaj. Pentru un punctaj de 75, mesajul afișat va fi "Ai primit nota C."

---

### 4. **Exemplu cu `switch`**

```java
int ziuaSaptamanii = 4;

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
    case 4:
        System.out.println("Joi");
        break;
    case 5:
        System.out.println("Vineri");
        break;
    case 6:
        System.out.println("Sâmbătă");
        break;
    case 7:
        System.out.println("Duminică");
        break;
    default:
        System.out.println("Zi necunoscută");
}
```
În acest exemplu, programul va afișa "Joi" deoarece variabila `ziuaSaptamanii` are valoarea 4. Dacă ar avea o altă valoare în afara intervalului 1-7, s-ar afișa "Zi necunoscută".

---

### 5. **Exemplu cu Ternary Operator (`?:`)**

```java
int vârstă = 20;
String status = (vârstă >= 18) ? "Adult" : "Minor";
System.out.println("Status: " + status);
```
Aici, operatorul ternar decide în funcție de valoarea variabilei `vârstă`. Dacă `vârstă` este 18 sau mai mare, `status` va fi "Adult"; altfel, va fi "Minor". În acest caz, se va afișa "Status: Adult".

---

### 6. **Exemplu cu `if` într-un context de verificare a unui an bisect**

```java
int an = 2024;

if ((an % 4 == 0 && an % 100 != 0) || (an % 400 == 0)) {
    System.out.println(an + " este an bisect.");
} else {
    System.out.println(an + " nu este an bisect.");
}
```
În acest exemplu, se verifică dacă un an este bisect. Pentru anul 2024, condiția este adevărată, așa că se va afișa "2024 este an bisect."

---

### 7. **Exemplu cu `if` pentru verificarea parității unui număr**

```java
int număr = 9;

if (număr % 2 == 0) {
    System.out.println("Numărul este par.");
} else {
    System.out.println("Numărul este impar.");
}
```
Acest cod verifică dacă un număr este par sau impar. În cazul numărului 9, va afișa "Numărul este impar."

---

### 8. **Exemplu cu `switch` pentru a selecta o operațiune matematică simplă**

```java
char operator = '+';
int număr1 = 5, număr2 = 3;
int rezultat;

switch (operator) {
    case '+':
        rezultat = număr1 + număr2;
        System.out.println("Rezultatul este: " + rezultat);
        break;
    case '-':
        rezultat = număr1 - număr2;
        System.out.println("Rezultatul este: " + rezultat);
        break;
    case '*':
        rezultat = număr1 * număr2;
        System.out.println("Rezultatul este: " + rezultat);
        break;
    case '/':
        rezultat = număr1 / număr2;
        System.out.println("Rezultatul este: " + rezultat);
        break;
    default:
        System.out.println("Operator necunoscut.");
}
```
În acest exemplu, pentru operatorul `+`, se va afișa "Rezultatul este: 8".

---

### 9. **Exemplu de combinare a mai multor condiții cu `if-else if-else`**

```java
int vârstă = 45;
boolean angajat = true;

if (vârstă < 18) {
    System.out.println("Nu este eligibil pentru muncă.");
} else if (vârstă >= 18 && angajat) {
    System.out.println("Este angajat.");
} else {
    System.out.println("Este adult, dar nu este angajat.");
}
```
Acest exemplu verifică dacă o persoană este minoră, angajată sau adultă, dar neangajată.

---

Aceste exemple acoperă o varietate de cazuri de utilizare a instrucțiunilor condiționale în Java, fiecare demonstrând cum poți controla fluxul execuției programului pe baza diferitelor condiții.
