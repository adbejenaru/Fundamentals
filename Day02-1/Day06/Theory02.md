**Imutabilitatea** în contextul `String`-urilor din Java înseamnă că odată creat un obiect de tip `String`, conținutul său nu poate fi modificat. Dacă încerci să schimbi un `String`, Java nu va modifica obiectul original, ci va crea un **nou obiect** `String` cu modificările dorite. Astfel, obiectele `String` sunt **fixe** (immutable), ceea ce oferă anumite avantaje în ceea ce privește securitatea, eficiența și gestionarea memoriei.

### De ce sunt `String`-urile imutabile?

1. **Securitate:** Deoarece `String`-urile sunt adesea folosite pentru a stoca informații sensibile (cum ar fi parolele, adresele URL, numele de utilizator), faptul că nu pot fi modificate le face mai sigure.
   
2. **Cache și reutilizare:** Java folosește un mecanism numit **string pool** pentru a reutiliza obiectele `String`. Dacă două variabile conțin aceeași secvență de caractere, ele pot împărți același obiect `String`, ceea ce economisește memorie. Imutabilitatea face acest lucru posibil, deoarece obiectele împărtășite nu pot fi schimbate accidental.

3. **Optimizarea performanței:** Deoarece `String`-urile sunt imutabile, ele pot fi utilizate în structuri de date eficiente, cum ar fi `HashMap` sau `HashSet`, fără a fi nevoie de recalcularea codurilor hash (deoarece nu se schimbă conținutul lor).

### Exemplu de imutabilitate:

```java
String text = "Salut";
text = text + " lume!";  // Acum s-a creat un nou String "Salut lume!"
```

În acest exemplu:
- Inițial, `text` este setat la "Salut".
- Când concatenezi " lume!" la `text`, Java creează un **nou** obiect `String` cu valoarea "Salut lume!" și îl reasignează variabilei `text`.
- Obiectul original "Salut" rămâne neschimbat, iar variabila `text` referențiază acum noul obiect "Salut lume!".

### Avantaje ale imutabilității:

- **Securitate**: Obiectele `String` nu pot fi modificate după creare, ceea ce previne modificările neintenționate sau rău intenționate.
- **Reutilizare eficientă**: Imutabilitatea permite reutilizarea aceluiași obiect `String` în diferite contexte, economisind memorie.
- **Thread-safety**: Deoarece `String`-urile nu pot fi modificate, ele sunt inerent sigure pentru utilizarea în aplicații multi-threaded fără sincronizare suplimentară.

### Concluzie:
Imutabilitatea stringurilor face manipularea textelor mai sigură și eficientă în Java. De fiecare dată când încerci să schimbi un `String`, Java creează un nou obiect, lăsând obiectul original neatins.
