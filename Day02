În Java, **metodele** sunt blocuri de cod care îndeplinesc o anumită sarcină. Ele pot fi folosite pentru a organiza și reutiliza codul într-un mod clar și eficient. Fiecare metodă are un nume, poate primi parametri (valori de intrare), poate returna o valoare (sau nu, în cazul metodelor `void`), și poate fi apelată ori de câte ori este nevoie în cadrul programului.

### Structura unei metode în Java:

1. **Modificatori de acces**: Determină cine poate apela metoda (public, private, protected).
2. **Tipul de retur**: Specifică ce tip de valoare va returna metoda (ex: `int`, `String`, `void` dacă nu returnează nimic).
3. **Numele metodei**: Reprezintă modul prin care metoda este identificată și apelată.
4. **Parametrii metodei**: Sunt valorile pe care metoda le poate primi pentru a opera cu ele. Aceștia sunt incluși între paranteze.
5. **Corpul metodei**: Reprezintă blocul de cod executat atunci când metoda este apelată.

### Exemplu de metodă:
```java
public int aduna(int a, int b) {
    return a + b;
}
```

### Explicație:
- **`public`**: Modificator de acces, indică faptul că metoda poate fi apelată de oriunde.
- **`int`**: Tipul de retur, în acest caz metoda returnează un număr de tip întreg.
- **`aduna`**: Numele metodei.
- **`int a, int b`**: Parametrii metodei, care sunt două numere întregi.
- **`return a + b;`**: Linia de cod care returnează suma celor două numere primite ca parametri.

### Tipuri de metode:
1. **Metode fără parametri și fără valoare de retur**:
   ```java
   public void afiseazaMesaj() {
       System.out.println("Salut!");
   }
   ```
   Această metodă nu primește parametri și nu returnează nimic, doar afișează un mesaj.

2. **Metode cu parametri și cu valoare de retur**:
   ```java
   public int inmulteste(int x, int y) {
       return x * y;
   }
   ```

3. **Metode `static`**:
   Aceste metode aparțin clasei și nu unei instanțe a clasei. Pot fi apelate fără a crea un obiect al clasei.
   ```java
   public static int adunare(int a, int b) {
       return a + b;
   }
   ```

### Beneficii:
- **Reutilizare**: Metodele pot fi apelate ori de câte ori este necesar în cadrul programului, evitând duplicarea codului.
- **Organizare**: Ele permit structurarea codului în secțiuni logice.
- **Modularitate**: Descompunerea unui program complex în metode mai mici și mai gestionabile ajută la întreținerea și testarea codului.
Pentru a folosi o metodă într-un program Java, aceasta poate fi apelată din metoda principală (`main`), care este punctul de intrare al unui program Java. Metoda `main` este responsabilă pentru inițializarea programului și apelarea altor metode.

### Exemplu simplu:

```java
public class Calculator {

    // O metodă care adună două numere
    public int aduna(int a, int b) {
        return a + b;
    }

    // Metoda principală a programului
    public static void main(String[] args) {
        // Creăm un obiect al clasei Calculator pentru a apela metode non-statice
        Calculator calc = new Calculator();
        
        // Apelăm metoda aduna și afișăm rezultatul
        int rezultat = calc.aduna(5, 7);
        System.out.println("Rezultatul adunării este: " + rezultat);
    }
}
```

### Explicație:
- **Metoda `aduna`**: Este o metodă non-statică (de instanță) care returnează suma a două numere.
- **Clasa `Calculator`**: Conține metoda `aduna` și metoda `main`, care inițializează aplicația.
- **Metoda `main`**: 
  - Este `static`, deci poate fi apelată direct fără a crea un obiect.
  - Creează un obiect al clasei `Calculator` (folosind `new Calculator()`), astfel încât să putem folosi metoda `aduna`.
  - Apelează metoda `aduna(5, 7)` și salvează rezultatul într-o variabilă `rezultat`.
  - Afișează rezultatul folosind `System.out.println`.

### Exemple suplimentare:

1. **Folosind o metodă statică** (nu necesită crearea unui obiect):
   ```java
   public class Operatii {

       // O metodă statică care înmulțește două numere
       public static int inmulteste(int x, int y) {
           return x * y;
       }

       public static void main(String[] args) {
           // Apelăm metoda statică direct, fără a crea un obiect
           int rezultat = inmulteste(4, 6);
           System.out.println("Rezultatul înmulțirii este: " + rezultat);
       }
   }
   ```

   - Aici, metoda `inmulteste` este `statică`, deci poate fi apelată direct în metoda `main` fără a crea un obiect al clasei `Operatii`.

2. **Metodă cu mai mulți parametri**:
   ```java
   public class Salutari {

       // Metodă care primește un nume și afișează un mesaj de salut
       public void afiseazaSalut(String nume, int varsta) {
           System.out.println("Salut, " + nume + "! Ai " + varsta + " ani.");
       }

       public static void main(String[] args) {
           // Creăm un obiect al clasei Salutari
           Salutari salut = new Salutari();
           
           // Apelăm metoda afiseazaSalut
           salut.afiseazaSalut("Adrian", 25);
       }
   }
   ```

   - Metoda `afiseazaSalut` primește doi parametri: un nume și o vârstă, apoi afișează un mesaj personalizat.

### Reține:
- **Metode statice**: Pot fi apelate direct în metoda `main` fără a crea un obiect al clasei.
- **Metode non-statice**: Necesită crearea unui obiect al clasei înainte de a putea fi apelate.

Acest exemplu îți clarifică modul în care metodele pot fi apelate în cadrul metodei `main`?
