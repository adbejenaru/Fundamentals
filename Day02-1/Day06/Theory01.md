În Java, un **`String`** este o clasă care reprezintă o secvență de caractere. Șirurile de caractere în Java sunt obiecte **imutabile**, ceea ce înseamnă că odată ce un obiect de tip `String` este creat, conținutul său nu poate fi modificat. Dacă încerci să schimbi valoarea unui `String`, se va crea un nou obiect `String`, iar cel original va rămâne neschimbat.

Iată câteva caracteristici importante ale clasei `String` în Java:

1. **Creare:** Poți crea un obiect `String` folosind fie ghilimele duble, fie constructorul clasei `String`.
   ```java
   String text = "Salut, lume!";  // crează un string literal
   String altText = new String("Salut!");  // folosește constructorul
   ```

2. **Imutabilitate:** Odată creat, conținutul unui `String` nu poate fi schimbat.
   ```java
   String text = "Salut";
   text = text + " lume!";  // Nu modifică string-ul inițial, creează unul nou
   ```

3. **Metode comune:** Clasa `String` vine cu o mulțime de metode utile pentru lucrul cu textul.
   - `length()` - returnează lungimea șirului.
   - `charAt(int index)` - returnează caracterul de la o anumită poziție.
   - `substring(int beginIndex, int endIndex)` - extrage o subsecvență de caractere.
   - `toUpperCase()` / `toLowerCase()` - convertește șirul în majuscule sau minuscule.

   ```java
   String text = "Java este grozav!";
   System.out.println(text.length());  // Afișează 17
   System.out.println(text.charAt(5));  // Afișează 'e'
   System.out.println(text.toUpperCase());  // Afișează 'JAVA ESTE GROZAV!'
   ```

4. **Concatenare:** Poți concatena două `String`-uri folosind operatorul `+`.
   ```java
   String text1 = "Bună";
   String text2 = " ziua!";
   String rezultat = text1 + text2;  // "Bună ziua!"
   ```

În concluzie, `String` este o clasă foarte puternică și flexibilă în Java pentru a lucra cu texte și secvențe de caractere.
