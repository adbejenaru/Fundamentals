### Regular Expressions (Expresii Regulate) - Introducere în Java

Expresiile regulate, cunoscute și sub numele de **regex**, reprezintă șabloane folosite pentru a verifica dacă un șir de caractere respectă un anumit format. În Java, acestea sunt utile pentru a valida datele introduse de utilizatori, precum verificarea dacă o adresă de email este corectă sau dacă un număr de telefon are formatul potrivit.

#### Ce sunt expresiile regulate?

Expresiile regulate sunt modele formate din secvențe de caractere sau simboluri speciale, care descriu structura unui șir de caractere. Ele sunt utile pentru:
- Căutare și potrivire de șiruri de caractere.
- Validarea formatului unor date (de exemplu, email, coduri poștale, parole).
- Înlocuirea sau modificarea anumitor secvențe dintr-un șir.

Exemplu simplu de expresie regulată pentru validarea unui nume:
```regex
"[A-Z][a-z]+"
```
Aceasta verifică dacă un nume începe cu o literă mare (`[A-Z]`), urmată de una sau mai multe litere mici (`[a-z]+`).

---

### Structura expresiilor regulate

Expresiile regulate constau dintr-o secvență de **atomi**:
- **Atom**: Elementul de bază al unei expresii regulate. Acesta poate fi:
  - O literă (`a`, `b`, etc.).
  - Un număr (`1`, `2`, etc.).
  - Un caracter special (`@`, `!`, etc.).
  
Atomi pot fi combinați pentru a forma grupuri sau secvențe, iar aceste grupuri pot fi restricționate cu **quantifiers** (quantificatori) care specifică de câte ori trebuie să apară atomul.

---

### Quantificatori (Quantifiers)

**Quantificatorii** descriu numărul de repetări al unui atom sau secvență într-un șir de caractere. De exemplu:
- `a+bcde`: Litera `a` trebuie să apară cel puțin o dată, urmată de secvența „bcde”.
  
Cele mai comune quantificatoare sunt:
- **`+`**: Apare de **cel puțin o dată**.
- **`*`**: Apare de **zero sau mai multe ori**.
- **`?`**: Apare de **zero sau o dată**.
- **`{n}`**: Apare exact de **n ori**.
- **`{n,m}`**: Apare de **cel puțin n și cel mult m ori**.

Exemplu:
```regex
a+bcde
```
Acest șablon caută un șir care începe cu una sau mai multe litere „a”, urmată de secvența „bcde”.

---

### Ranges (Intervale) și Groups (Grupuri)

**Intervalele** și **grupurile** sunt alte instrumente utile în expresiile regulate.

1. **Intervale**:
   - Permit definirea unui set de caractere care sunt permise într-o poziție anume.
   - Se definesc între paranteze pătrate: `[ ]`.
   - Pot include fie o listă de caractere (de exemplu, `[abc]`), fie un interval de caractere (de exemplu, `[a-z]`).

   Exemple:
   - **`[0-9]`**: Un singur caracter care este o cifră.
   - **`[a-z]`**: O literă mică.
   - **`[A-Z]`**: O literă mare.

2. **Grupuri**:
   - Caracterele pot fi grupate între paranteze rotunde: `( )`.
   - Grupurile sunt utile pentru a aplica quantificatori sau pentru a capta subșiruri din șirul original.

Exemple de intervale în expresii regulate:
- `[0-9]`: Orice cifră între 0 și 9.
- `[a-z]`: Orice literă mică.
- `[A-Z]`: Orice literă mare.

---

### Implementarea expresiilor regulate în Java

În Java, expresiile regulate sunt utilizate cu ajutorul claselor **Pattern** și **Matcher**, ambele din pachetul `java.util.regex`.

1. **Pattern**:
   - **Pattern** este o clasă care reprezintă o expresie regulată compilată.
   - Folosim metoda statică `compile()` pentru a crea un obiect `Pattern` pe baza unui șir care reprezintă o expresie regulată.

   Exemplu:
   ```java
   Pattern pattern = Pattern.compile("a+bcd");
   ```

2. **Matcher**:
   - **Matcher** este o clasă care verifică dacă un șir se potrivește cu un `Pattern`.
   - Metoda `matcher()` a clasei `Pattern` returnează un obiect `Matcher` care poate fi folosit pentru a verifica potrivirile într-un șir.
   - Metode importante din clasa `Matcher`:
     - **matches()**: Verifică dacă șirul întreg se potrivește cu expresia regulată.
     - **find()**: Caută dacă există vreo secvență în șirul de caractere care se potrivește cu expresia regulată.

   Exemplu:
   ```java
   Pattern pattern = Pattern.compile("a+bcd");
   Matcher matcher = pattern.matcher("aaaaabcd aaaaaaabbcd");
   matcher.matches();  // returnează true/false
   ```

   De asemenea, **`find()`** este util pentru a căuta secvențe în șiruri lungi:
   ```java
   matcher.find();  // returnează true/false
   ```

---

### Recapitulare

- **Expresiile regulate** sunt modele care ajută la identificarea formatului unui șir de caractere.
- **Quantificatorii** determină de câte ori trebuie să apară un atom sau un grup.
- **Intervalele** sunt folosite pentru a specifica un set de caractere posibile într-o poziție anume.
- În Java, folosim clasele **Pattern** și **Matcher** pentru a lucra cu expresii regulate. 

Expresiile regulate sunt extrem de utile în situații precum validarea formatului datelor, căutarea de pattern-uri în text sau înlocuirea unor secvențe într-un șir.
