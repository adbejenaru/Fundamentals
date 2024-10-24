Iată un task practic care folosește **varargs** în Java:

### Task: Aplică reduceri pentru mai multe produse

Scrie un program care calculează prețul final al mai multor produse după aplicarea unei reduceri procentuale. Programul ar trebui să facă următoarele:

1. Permite utilizatorului să introducă un număr variabil de prețuri ale produselor.
2. Permite introducerea unui procent de reducere.
3. Calculează și afișează prețurile finale după aplicarea reducerii pentru fiecare produs.
4. Afișează prețul total al tuturor produselor după reducere.

### Cerințe:
- Scrie o metodă care folosește **varargs** pentru a accepta un număr variabil de prețuri.
- Aplică un procent de reducere la fiecare preț.
- Afișează prețurile finale și prețul total după reducere.

### Exemplu de rezultat:
```
Prețuri înainte de reducere: 100.0, 200.0, 150.0
Reducere: 10%
Prețuri după reducere: 
Produs 1: 90.0
Produs 2: 180.0
Produs 3: 135.0
Preț total după reducere: 405.0
```

### Pași:
1. Creează o metodă `aplicaReducere(double reducere, double... preturi)` care aplică reducerea la toate prețurile primite.
2. Calculează prețul final pentru fiecare produs și totalul.

### Cod Java:

```java
public class DiscountCalculator {
    public static void main(String[] args) {
        // Prețurile produselor
        double reducere = 10.0;  // Reducere de 10%
        
        // Aplica reducerea pentru un set de produse
        aplicaReducere(reducere, 100.0, 200.0, 150.0);
    }

    static void aplicaReducere(double reducere, double... preturi) {
        System.out.println("Prețuri înainte de reducere:");
        for (double pret : preturi) {
            System.out.println(pret);
        }

        double totalDupaReducere = 0.0;
        System.out.println("\nPrețuri după aplicarea reducerii de " + reducere + "%:");
        for (int i = 0; i < preturi.length; i++) {
            double pretRedus = preturi[i] - (preturi[i] * reducere / 100);
            System.out.println("Produs " + (i + 1) + ": " + pretRedus);
            totalDupaReducere += pretRedus;
        }

        System.out.println("\nPreț total după reducere: " + totalDupaReducere);
    }
}
```

### Explicație:
1. **Varargs** permite metodei `aplicaReducere` să primească un număr variabil de prețuri.
2. Se calculează prețul redus pentru fiecare produs, iar rezultatul este afișat.
3. Programul afișează și prețul total după aplicarea reducerii la toate produsele.

Acest task este util pentru a calcula rapid reduceri pe mai multe produse simultan.
