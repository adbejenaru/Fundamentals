Iată o explicație detaliată despre array-uri în Java, incluzând tipurile, declarația, accesul la elemente și obținerea lungimii:

---

### 1. **Tipuri de Array-uri**

Un **array** (tablou) este o structură de date care poate stoca mai multe valori de același tip. În Java, array-urile sunt de tip **non-primitiv** și stochează elementele într-o zonă continuă de memorie.

#### Tipuri de Array-uri:

1. **Array-uri Unidimensionale**: Cel mai comun tip de array, o singură colecție liniară de elemente.
   ```java
   int[] numere = new int[5]; // Array unidimensional de 5 elemente de tip int
   ```

2. **Array-uri Multidimensionale**: Array-uri care conțin alte array-uri, de exemplu, matricele.
   - **Array-uri bidimensionale** (ca o matrice):
     ```java
     int[][] matrice = new int[3][3]; // Matrice 3x3
     ```

   - **Array-uri n-dimensionale** (cu mai multe dimensiuni):
     ```java
     int[][][] array3D = new int[3][3][3]; // Array tridimensional 3x3x3
     ```

3. **Array-uri Jagged (neuniforme)**: Un array bidimensional în care sub-array-urile pot avea lungimi diferite.
   ```java
   int[][] jaggedArray = new int[3][];
   jaggedArray[0] = new int[2];
   jaggedArray[1] = new int[4];
   jaggedArray[2] = new int[3];
   ```

---

### 2. **Declararea unui Array**

În Java, array-urile pot fi declarate și inițializate în mai multe moduri:

1. **Declarare și Inițializare cu o Dimensiune Specifică**: Definești dimensiunea array-ului la momentul inițializării.
   ```java
   int[] numere = new int[5]; // Array de 5 elemente de tip int, toate inițializate implicit la 0
   ```

2. **Declarare și Inițializare cu Valori Specificate**: Array-ul este creat automat cu dimensiunea necesară pentru a stoca toate valorile specificate.
   ```java
   int[] numere = {1, 2, 3, 4, 5}; // Array cu 5 elemente și valori presetate
   ```

3. **Declararea fără Inițializare**: Array-ul este declarat, dar inițializat mai târziu.
   ```java
   int[] numere;
   numere = new int[5];
   ```

4. **Array Multidimensional**: Poți declara array-uri cu mai multe dimensiuni.
   ```java
   int[][] matrice = new int[3][3]; // Matrice bidimensională 3x3
   ```

---

### 3. **Accesarea Elementelor din Array**

Fiecare element dintr-un array poate fi accesat folosind indicele său. Indicii array-urilor în Java încep de la `0`.

- **Accesarea unui Element**: Folosești numele array-ului și indicele elementului dorit.
  ```java
  int[] numere = {10, 20, 30, 40, 50};
  System.out.println(numere[0]); // Afișează 10
  System.out.println(numere[2]); // Afișează 30
  ```

- **Modificarea unui Element**: Poți schimba valoarea unui element specificând noua valoare pentru acel index.
  ```java
  numere[1] = 25; // Setează al doilea element (index 1) la valoarea 25
  ```

#### Accesarea Elementelor într-un Array Bidimensional:
Pentru un array bidimensional, folosești două indici pentru a accesa elementele.

```java
int[][] matrice = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
System.out.println(matrice[1][2]); // Afișează 6 (elementul de pe rândul 2, coloana 3)
```

---

### 4. **Lungimea unui Array**

Array-urile în Java au o proprietate `length` care îți permite să afli câte elemente conține array-ul.

- **Lungimea unui Array Unidimensional**:
  ```java
  int[] numere = {1, 2, 3, 4, 5};
  System.out.println("Lungimea array-ului este: " + numere.length); // Afișează 5
  ```

- **Lungimea unui Array Bidimensional**:
  - `matrice.length` va da numărul de rânduri (dimensiunea primului nivel).
  - `matrice[i].length` va da numărul de coloane pentru rândul `i`.

  ```java
  int[][] matrice = {
      {1, 2, 3},
      {4, 5, 6}
  };
  System.out.println("Numărul de rânduri: " + matrice.length); // Afișează 2
  System.out.println("Numărul de coloane în primul rând: " + matrice[0].length); // Afișează 3
  ```

---

### Recapitulare

- **Declarare**: `int[] array = new int[5];`
- **Accesare**: `array[0] = 10;`
- **Lungime**: `array.length` îți spune câte elemente sunt în array.

Array-urile oferă un mod eficient de a gestiona colecții de elemente de același tip și sunt folosite frecvent în Java pentru gestionarea datelor.
