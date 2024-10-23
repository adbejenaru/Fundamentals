### Clase

Clasele sunt folosite pentru a descrie obiecte, activități, stări și relațiile dintre acestea în programele Java. Ele reprezintă un șablon care definește structura și comportamentul obiectelor dintr-o aplicație.

O clasă are două componente principale:
1. **Câmpuri (fields)**: Acestea sunt variabile care descriu proprietățile unui obiect. De exemplu, un obiect de tip Mașină poate avea câmpuri precum culoare, model, sau viteză maximă.
2. **Metode (methods)**: Acestea reprezintă acțiuni sau operațiuni pe care un obiect le poate efectua. De exemplu, o metodă pentru o mașină poate fi `pornește()`.

#### Exemplar simplu de clasă
```java
public class Film {              
    private String titlu;        
    private String descriere;    
    private int anProductie;    

    public void ruleaza() {      
        System.out.println("Filmul rulează.");
    }
}
```
În exemplul de mai sus, clasa `Film` descrie un obiect de tip film, cu atributele sale (`titlu`, `descriere` și `anProductie`) și o metodă (`ruleaza()`) care simulează redarea filmului.

#### Exemplu mai complex de clasă
```java
public class Telefon {
    private String marca;
    private String model;
    private int capacitateBaterie;

    public void setMarca(String marca) {
        this.marca = marca;
    }

    public void setModel(String model) {
        this.model = model;
    }

    public void setCapacitateBaterie(int capacitateBaterie) {
        this.capacitateBaterie = capacitateBaterie;
    }

    public void afiseazaDetaliiTelefon() {
        System.out.println("Telefon: " + marca + " " + model + ", baterie: " + capacitateBaterie + "mAh");
    }
}
```
Acest exemplu include metode care permit setarea detaliilor telefonului și o metodă care afișează aceste informații.

### Obiecte

Un **obiect** este o instanță a unei clase. Obiectele sunt create folosind **constructori**, care sunt metode speciale din clasă pentru inițializarea câmpurilor. De exemplu, pentru a crea un obiect de tip `Telefon`:

```java
Telefon telefon1 = new Telefon();  // Creăm un obiect nou de tip Telefon
```
Odată creat obiectul, poți seta atributele sale și poți apela metode:

```java
telefon1.setMarca("Samsung");
telefon1.setModel("Galaxy S21");
telefon1.setCapacitateBaterie(4000);
telefon1.afiseazaDetaliiTelefon();
```

### Modificatori de acces

Modificatorii de acces controlează vizibilitatea și accesul la câmpurile și metodele unei clase. În Java, există patru modificatori principali:

1. **`public`**: Oferă acces de oriunde în aplicație.
2. **`private`**: Restricționează accesul doar la interiorul clasei în care sunt definite.
3. **`protected`**: Permite accesul din interiorul aceleași clase, pachetului și subclaselor (moștenite).
4. **(implicit - package-private)**: Accesibil doar din clasele aflate în același pachet.

#### Exemplu cu modificatori de acces
```java
public class Carte {
    public String titlu;    // Accesibil de oriunde
    private int numarPagini;  // Accesibil doar din clasa Carte

    public void setNumarPagini(int numarPagini) {
        if (numarPagini > 0) {
            this.numarPagini = numarPagini;
        } else {
            System.out.println("Numărul de pagini trebuie să fie pozitiv.");
        }
    }
}
```
În acest exemplu, `titlu` este public, deci poate fi accesat de oriunde, dar `numarPagini` este privat și poate fi modificat doar prin metoda `setNumarPagini()`.

### Getteri și setteri

Gettere și settere sunt metode utilizate pentru a accesa și modifica valorile câmpurilor private ale unei clase, respectând principiul încapsulării.

```java
public class Carte {
    private String titlu;
    private String autor;

    public String getTitlu() {
        return titlu;
    }

    public void setTitlu(String titlu) {
        this.titlu = titlu;
    }

    public String getAutor() {
        return autor;
    }

    public void setAutor(String autor) {
        this.autor = autor;
    }
}
```
Aceste metode asigură că valorile câmpurilor pot fi accesate și modificate doar prin metode bine definite.

### Pachete

Pachetele în Java sunt folosite pentru a organiza clasele și a evita conflictele între numele de clase. De exemplu, poți avea două clase cu același nume, dar în pachete diferite:

```java
package biblioteca.literatura;

public class Carte {
    // Definiții
}
```
Într-o altă parte a proiectului:
```java
package biblioteca.tehnica;

public class Carte {
    // Definiții
}
```

### Constructori

Un **constructor** este o metodă specială folosită pentru a inițializa obiectele. Constructorii au același nume ca și clasa și nu returnează valori. Ei sunt folosiți pentru a seta valorile inițiale ale câmpurilor unui obiect.

#### Exemplu de constructor
```java
public class Masina {
    private String marca;
    private int vitezaMaxima;

    public Masina(String marca, int vitezaMaxima) {
        this.marca = marca;
        this.vitezaMaxima = vitezaMaxima;
    }

    public void afiseazaDetalii() {
        System.out.println("Marca: " + marca + ", Viteza maximă: " + vitezaMaxima);
    }
}
```

### Metode și clase statice

**Metodele statice** pot fi apelate fără a crea un obiect al clasei. Acestea sunt utile pentru funcționalități generale care nu depind de starea unui obiect.

```java
public class Calculator {
    public static int aduna(int a, int b) {
        return a + b;
    }
}

public class TestCalculator {
    public static void main(String[] args) {
        int rezultat = Calculator.aduna(5, 3);
        System.out.println("Rezultatul este: " + rezultat);
    }
}
```

Metodele statice sunt apelate folosind numele clasei, nu al unui obiect.

Acestea sunt conceptele fundamentale despre clase, obiecte și modificatori de acces în Java, explicate cu alte exemple pentru o mai bună înțelegere.
