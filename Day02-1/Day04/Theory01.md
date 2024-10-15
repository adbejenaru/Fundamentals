![image](https://github.com/user-attachments/assets/d03c8bc8-8fe7-4119-b6ad-78472d151874)
Imaginea ilustrează fluxul unui bloc de cod care folosește o declarație `if`. Acest tip de diagramă descrie modul în care programul decide dacă va executa sau nu o secțiune de cod în funcție de evaluarea unei condiții.

### Explicația diagramei:
1. **Condition (Condiție)**:
   - Programul începe prin evaluarea unei condiții. Această condiție este o expresie booleană care poate fi fie `true` (adevărată), fie `false` (falsă).
   
2. **IF Statement Block**:
   - Dacă **condiția** este `true`, se execută blocul de cod care se află în instrucțiunea `if`.
   
3. **Rest of the Program (Restul Programului)**:
   - După executarea blocului `if`, programul continuă să execute restul codului.
   - Dacă **condiția** este `false`, programul va sări peste blocul `if` și va continua direct cu restul programului.

### Explicație cu exemplu de cod:

```java
public class ExempluIf {
    public static void main(String[] args) {
        int varsta = 18;
        
        // Condiția
        if (varsta >= 18) {
            // Blocul de cod din if este executat doar dacă condiția este adevărată
            System.out.println("Ești major.");
        }
        
        // Restul programului care se execută indiferent de condiție
        System.out.println("Programul continuă...");
    }
}
```

### Explicație a fluxului:
1. **Condiția** este `varsta >= 18`. Programul verifică dacă această condiție este adevărată.
   - Dacă `varsta` este 18 sau mai mare, atunci condiția este `true`, și mesajul `"Ești major."` va fi afișat.
   - Dacă `varsta` ar fi mai mică de 18, atunci condiția ar fi `false`, și acest mesaj nu ar fi afișat.

2. **Blocul `if`**:
   - Dacă condiția este adevărată, instrucțiunea din blocul `if` va fi executată, în acest caz se va afișa `"Ești major."`.

3. **Restul programului**:
   - Indiferent dacă blocul `if` a fost executat sau nu, programul va afișa `"Programul continuă..."`, pentru că acesta este restul codului care se execută indiferent de rezultat.

### Exemplu cu ieșire:
Dacă `varsta = 18`, ieșirea va fi:
```
Ești major.
Programul continuă...
```

Dacă `varsta = 16`, ieșirea va fi:
```
Programul continuă...
``` 

Astfel, în funcție de condiția dată, se decide dacă blocul de cod din `if` va fi executat sau nu.
![image](https://github.com/user-attachments/assets/3aafeaf7-503a-484d-90ea-3c360d6190fd)

Imaginea arată fluxul unui bloc de cod care utilizează o instrucțiune **`if-else`**. Aceasta este o extindere a structurii simple `if`, unde, dacă condiția evaluată este **falsă**, se va executa un bloc de cod alternativ definit în instrucțiunea **`else`**.

### Explicația diagramei:

1. **Statement (Declarație/Condiție)**:
   - La fel ca în cazul blocului `if`, programul începe prin evaluarea unei **condiții**. Această condiție este o expresie booleană care poate fi fie `true` (adevărată), fie `false` (falsă).
   
2. **IF Block Instructions**:
   - Dacă **condiția** este `true`, se execută blocul de cod din instrucțiunea `if`.

3. **Else Block Instructions**:
   - Dacă **condiția** este `false`, se execută blocul de cod din instrucțiunea `else`.

4. **Restul Programului**:
   - După ce se execută fie blocul `if`, fie blocul `else`, programul continuă cu restul codului.

### Explicație cu exemplu de cod:

```java
public class ExempluIfElse {
    public static void main(String[] args) {
        int varsta = 16;
        
        // Condiția
        if (varsta >= 18) {
            // Blocul de cod din if este executat dacă condiția este adevărată
            System.out.println("Ești major.");
        } else {
            // Blocul de cod din else este executat dacă condiția este falsă
            System.out.println("Nu ești major.");
        }
        
        // Restul programului care se execută indiferent de condiție
        System.out.println("Programul continuă...");
    }
}
```

### Explicație a fluxului:
1. **Condiția** este `varsta >= 18`. Programul verifică dacă această condiție este adevărată.
   - Dacă `varsta` este 18 sau mai mare, atunci condiția este `true` și mesajul `"Ești major."` va fi afișat.
   - Dacă `varsta` este mai mică de 18, atunci condiția este `false` și mesajul `"Nu ești major."` va fi afișat.

2. **Blocul `else`**:
   - Dacă condiția este `false`, instrucțiunea din blocul `else` va fi executată, afișând mesajul `"Nu ești major."`.

3. **Restul programului**:
   - Indiferent dacă blocul `if` sau blocul `else` a fost executat, programul va afișa `"Programul continuă..."` pentru că acesta este restul codului care se execută indiferent de rezultat.

### Exemplu cu ieșire:
Dacă `varsta = 16`, ieșirea va fi:
```
Nu ești major.
Programul continuă...
```

Dacă `varsta = 19`, ieșirea va fi:
```
Ești major.
Programul continuă...
```

### Observații:
- Structura `if-else` este utilă atunci când ai nevoie de două căi posibile: o cale pentru când condiția este adevărată și o altă cale pentru când condiția este falsă.
- După ce se execută fie blocul `if`, fie blocul `else`, programul continuă cu restul instrucțiunilor.
