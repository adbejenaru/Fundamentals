Observ că în cazul tău, codul funcționează fără să fie necesar apelul la `scanner.nextLine()` pentru a consuma newline-ul, cel puțin pentru combinația de tipuri de date `nextInt()` urmat de `nextDouble()`. Acest lucru se poate întâmpla datorită unor circumstanțe particulare legate de cum se comportă bufferul `Scanner` în anumite situații, dar asta nu înseamnă că nu te-ai putea confrunta cu această problemă în alte contexte.

### De ce funcționează acum fără `scanner.nextLine()`?

1. **Cazul `nextInt()` urmat de `nextDouble()`**:
   - În acest caz, se pare că Java gestionează bine tranziția de la citirea unui număr întreg (`nextInt()`) la un număr zecimal (`nextDouble()`) deoarece ambele citesc valori numerice și nu fac apel imediat la metode care ar citi linia întreagă, precum `nextLine()`.

2. **De ce funcționează în cazul tău?**:
   - Când treci de la citirea unui număr întreg la un număr zecimal, metoda `nextDouble()` preia pur și simplu următoarea valoare din buffer, fără să aibă nevoie de o linie întreagă, ceea ce elimină necesitatea de a consuma explicit newline-ul.

### Când poate fi necesar apelul la `scanner.nextLine()`:
Problema apare atunci când, după apelul la `nextInt()` sau `nextDouble()`, vrei să citești o linie completă de text folosind `nextLine()`. În acest caz, newline-ul rămas după `nextInt()`/`nextDouble()` ar putea cauza comportamente neașteptate, cum ar fi să "sară" peste inputul textului.

### Exemplu unde ar fi necesar:

```java
System.out.print("Introdu un numar intreg: ");
int numarIntreg = scanner.nextInt();  // Consumă doar numărul
System.out.print("Introdu un text: ");
String text = scanner.nextLine();  // Acum va citi newline-ul rămas în buffer
```

În acest caz, `nextLine()` va citi newline-ul rămas în buffer și va returna un șir gol. Aici, apelul suplimentar la `scanner.nextLine()` ar fi necesar.

### Concluzie:
În cazul tău particular, în care citești un număr întreg urmat de un număr zecimal, apelul la `scanner.nextLine()` nu este necesar, deoarece ambele metode citesc doar valori numerice, fără a lăsa newline-uri problematice în buffer. Totuși, dacă în viitor vei combina aceste citiri cu text (folosind `nextLine()`), vei avea nevoie să consumi newline-ul rămas după `nextInt()` sau `nextDouble()`.
