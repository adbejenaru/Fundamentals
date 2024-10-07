Slide-urile furnizate explică diferite tipuri de variabile în Java și modul în care acestea funcționează în cadrul claselor și metodelor. Iată explicațiile clare pentru fiecare slide:

### 1. **Variabile globale într-o clasă ('Global' variables within a class)**
   - O **variabilă globală** este declarată în afara metodelor, dar în interiorul clasei. Aceasta poate fi folosită în orice metodă a acelei clase.
   - În exemplul dat:
     ```java
     class ExampleClass {
         int myGlobal = 12; // Variabilă globală
         void someMethod() {
             // Poți folosi variabila myGlobal aici
             System.out.print("My global variable: " + myGlobal);
         }
     }
     ```
     - **myGlobal** este o variabilă globală care poate fi accesată și modificată de orice metodă din clasa `ExampleClass`.

### 2. **Variabile locale într-o metodă ('Local' variables within the methods)**
   - O **variabilă locală** este declarată în interiorul unei metode și poate fi folosită doar în acea metodă. Nu este accesibilă din afara metodei în care a fost definită.
   - În exemplu:
     ```java
     class ExampleClass {
         void someMethod() {
             int myLocalVariable = 5; // Variabilă locală
             System.out.print("My local variable: " + myLocalVariable);
         }
         int myGlobal = myLocalVariable; // Eroare – variabila locală nu este vizibilă aici
     }
     ```
     - **myLocalVariable** este o variabilă locală și nu poate fi accesată în afara metodei `someMethod`. În afara metodei, va genera o eroare dacă încerci să o folosești.

### 3. **Variabile locale în instrucțiuni de control de flux ('Local' variables declared inside flow control instructions)**
   - Variabilele locale pot fi declarate în cadrul instrucțiunilor de control de flux, cum ar fi condițiile `if` și buclele `for`. Aceste variabile sunt vizibile doar în interiorul acelor blocuri de cod.
   - În exemplu:
     ```java
     class MyExampleClass {
         void someExampleMethod() {
             if (someCondition) {
                 int a = 1; // Variabilă locală în blocul 'if'
             }
             for (int i = 0; i < 10; i++) {
                 // Variabila 'i' este vizibilă doar în această buclă
             }
         }
     }
     ```
     - **a** este o variabilă locală care există doar în cadrul condiției `if`.
     - **i** este o variabilă locală definită în bucla `for`, vizibilă doar în acea buclă.

### 4. **Variabile finale ('Final' variables)**
   - O variabilă **final** este o variabilă care nu poate fi modificată după ce a fost inițializată. Odată ce i-ai atribuit o valoare, aceasta rămâne constantă pe toată durata programului.
   - În exemplu:
     ```java
     final int finalVariable = 25; // Variabilă finală inițializată cu 25
     
     private void finalVariableSample() {
         final int finalVariable = 123; // Variabilă finală
         finalVariable = 12; // Eroare de compilare – nu poți schimba valoarea unei variabile finale
     }
     ```
     - În interiorul metodei `finalVariableSample`, încercarea de a modifica valoarea unei variabile finale duce la o **eroare de compilare**, deoarece valoarea ei nu poate fi schimbată după inițializare.

Aceste slide-uri oferă o perspectivă clară asupra tipurilor de variabile din Java și limitările acestora, în funcție de locul unde sunt declarate și modul în care sunt utilizate.
