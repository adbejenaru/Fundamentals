În Java, **conversia de tipuri** și **casting-ul** sunt mecanisme folosite pentru a transforma un tip de date într-un alt tip de date. Acestea sunt utile atunci când trebuie să lucrăm cu tipuri de date diferite, iar Java oferă două modalități principale de conversie: conversia **implicită** și conversia **explicită** (casting). 

### 1. Conversia implicită (Widening)
Conversia implicită apare atunci când un tip de date mai mic este convertit automat într-un tip de date mai mare. Java face această conversie automat deoarece nu există riscul de pierdere a datelor. Aceasta este cunoscută și sub denumirea de **widening conversion** (extinderea tipului).

#### Exemplu:
```java
int numarInt = 100;
long numarLong = numarInt; // Conversie implicită de la int la long

System.out.println("Numar long: " + numarLong);
```

În exemplul de mai sus, tipul `int` este convertit automat la tipul `long` deoarece `long` este mai mare decât `int` și nu există pierderi de date.

### 2. Conversia explicită (Casting)
Conversia explicită, sau **casting-ul**, este necesară atunci când dorim să transformăm un tip de date mai mare într-unul mai mic. Acest proces poate duce la pierderea de date, așa că trebuie făcut manual folosind sintaxa de casting.

#### Exemplu:
```java
double numarDouble = 9.78;
int numarInt = (int) numarDouble; // Casting explicit de la double la int

System.out.println("Numar int: " + numarInt); // Afișează doar partea întreagă: 9
```

În acest exemplu, un `double` este transformat într-un `int` prin casting. Se pierde partea fracționară (0.78), deci rezultatul va fi doar partea întreagă.

### Tipuri de conversii:

1. **Widening (Extindere)**
   - Are loc automat (implicit).
   - Tipurile de date implicate devin mai mari.
   - Exemplu: de la `byte` la `int`, `int` la `double`, etc.

2. **Narrowing (Reducere)**
   - Necesită casting explicit.
   - Tipurile de date implicate devin mai mici.
   - Exemplu: de la `double` la `int`, de la `long` la `short`.

### Alte exemple de conversii:

#### Conversie de la `char` la `int` (implicit):
```java
char caracter = 'A';
int codASCII = caracter; // Conversie implicită de la char la int (ASCII)
System.out.println("Cod ASCII: " + codASCII); // Va afișa 65
```

#### Conversie de la `float` la `int` (casting explicit):
```java
float numarFloat = 5.99f;
int numarInt = (int) numarFloat; // Casting de la float la int
System.out.println("Numar int: " + numarInt); // Va afișa 5, partea fracționară se pierde
```

### Concluzie:
- **Conversia implicită** (widening) se face automat, fără pierderi de date.
- **Casting-ul explicit** (narrowing) este necesar atunci când trecem de la un tip de date mai mare la unul mai mic, dar poate cauza pierderi de date.

Este important să știi când să folosești fiecare metodă de conversie pentru a evita erori sau pierderi nedorite de date.


Desigur! Iată mai multe exemple care ilustrează **conversia de tipuri** și **casting-ul** în Java, în diferite scenarii:

### 1. **Conversie implicită (widening)** între tipuri numerice

Java poate efectua automat conversii între tipuri numerice compatibile, unde tipul de date țintă este mai mare decât tipul de date sursă.

#### Exemplu: De la `byte` la `int`
```java
byte numarMic = 42;
int numarMare = numarMic; // Conversie implicită de la byte la int
System.out.println("Număr mare (int): " + numarMare);
```
Această conversie este implicită, deoarece `int` este un tip de date mai mare decât `byte`.

#### Exemplu: De la `int` la `double`
```java
int numarInt = 123;
double numarDouble = numarInt; // Conversie implicită de la int la double
System.out.println("Număr double: " + numarDouble); // Afișează 123.0
```
În acest caz, conversia este automată deoarece `double` este mai mare și nu implică pierderi de date.

### 2. **Casting explicit (narrowing)** între tipuri numerice

Conversia explicită (casting) este necesară când se face trecerea de la un tip de date mai mare la unul mai mic, ceea ce poate duce la pierderi de precizie.

#### Exemplu: De la `double` la `int`
```java
double numarDouble = 123.456;
int numarInt = (int) numarDouble; // Casting explicit de la double la int
System.out.println("Număr int: " + numarInt); // Afișează 123, pierzând partea fracționară
```
În acest caz, partea zecimală (0.456) se pierde.

#### Exemplu: De la `long` la `short`
```java
long numarLong = 10000L;
short numarShort = (short) numarLong; // Casting explicit de la long la short
System.out.println("Număr short: " + numarShort); // Afișează 10000
```
În acest exemplu, nu există pierderi de date, deoarece valoarea poate fi reprezentată corect într-un `short`.

### 3. **Conversie între `char` și `int`**

Caracterele (`char`) sunt stocate în format numeric conform tabelei ASCII, așa că pot fi convertite la și din tipuri numerice.

#### Exemplu: De la `char` la `int`
```java
char litera = 'B';
int codASCII = litera; // Conversie implicită de la char la int (cod ASCII)
System.out.println("Cod ASCII pentru 'B': " + codASCII); // Afișează 66
```
În acest caz, caracterul `'B'` este convertit automat la codul său ASCII, care este 66.

#### Exemplu: De la `int` la `char`
```java
int codASCII = 67;
char litera = (char) codASCII; // Casting explicit de la int la char
System.out.println("Caracter pentru codul ASCII 67: " + litera); // Afișează 'C'
```
Aici, folosim casting explicit pentru a transforma codul ASCII înapoi într-un caracter.

### 4. **Conversie între tipuri numerice și `String`**

Conversia între tipuri de date primitive și șiruri de caractere (`String`) poate fi realizată cu ajutorul unor metode specifice, cum ar fi `String.valueOf()` sau `Integer.parseInt()`.

#### Exemplu: De la `int` la `String`
```java
int numar = 100;
String text = String.valueOf(numar); // Conversie de la int la String
System.out.println("Text: " + text); // Afișează "100"
```

#### Exemplu: De la `String` la `int`
```java
String text = "123";
int numar = Integer.parseInt(text); // Conversie de la String la int
System.out.println("Număr: " + numar); // Afișează 123
```
Această conversie presupune că șirul de caractere poate fi interpretat ca un număr valid.

### 5. **Casting între tipuri de referință (obiecte)**

În cazul tipurilor de referință (obiecte), Java permite casting-ul între clase care au o relație de moștenire (ex: părinte și copil). Există două tipuri de casting între obiecte:

- **Upcasting**: Convertirea unui tip de obiect copil într-un tip părinte (implicit).
- **Downcasting**: Convertirea unui tip de obiect părinte într-un tip copil (necesită casting explicit).

#### Exemplu: Upcasting (implicit)
```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}

Animal myDog = new Dog(); // Upcasting implicit de la Dog la Animal
myDog.sound(); // Va afișa "Dog barks", deoarece metoda este suprascrisă
```

#### Exemplu: Downcasting (explicit)
```java
Animal myAnimal = new Dog(); // Upcasting implicit
Dog myDog = (Dog) myAnimal; // Downcasting explicit de la Animal la Dog
myDog.sound(); // Va afișa "Dog barks"
```
Este important să te asiguri că obiectul care este downcastat este cu adevărat de tipul specificat, altfel vei obține o eroare `ClassCastException`.

### 6. **Conversie de la `double` la `float` (casting explicit)**
```java
double numarDouble = 9.87654321;
float numarFloat = (float) numarDouble; // Casting explicit de la double la float
System.out.println("Număr float: " + numarFloat); // Afișează aproximativ 9.876543
```
Aceasta este o conversie explicită, deoarece `float` are o precizie mai mică decât `double`.

### Concluzie

- Conversiile implicite (widening) au loc automat și sunt sigure.
- Conversiile explicite (narrowing) trebuie făcute manual folosind casting și pot duce la pierderi de date.
- În cazul obiectelor, poți face **upcasting** și **downcasting**, dar **downcasting-ul** necesită atenție pentru a evita erorile de tip `ClassCastException`.

Aceste exemple arată cum funcționează diferitele tipuri de conversii și casting în Java și cum să le utilizezi corect în funcție de nevoile tale.
