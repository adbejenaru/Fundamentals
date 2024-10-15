![image](https://github.com/user-attachments/assets/e02d534a-d4a2-438b-bef7-59cc2fe4cc41)

Imaginea afișează o diagramă care ilustrează conversiile implicite (widening) între diferite tipuri primitive în Java. Să analizăm ce reprezintă aceste săgeți:

- **Conversii de la tipuri mai mici la tipuri mai mari**:
  - `byte` poate fi convertit implicit în `short`.
  - `short` poate fi convertit implicit în `int`.
  - `char` poate fi convertit în `int`.
  - `int` poate fi convertit în `long`, `float`, sau `double`.
  - `long` poate fi convertit în `float` sau `double`.
  - `float` poate fi convertit în `double`.

Aceasta înseamnă că, în Java, poți face aceste conversii fără să fie nevoie de casting explicit, deoarece Java gestionează aceste conversii automat și nu există riscul pierderii de date.

### Exemple de conversii implicite bazate pe diagramă:

1. **Conversie de la `byte` la `short`**:
   ```java
   byte numarByte = 10;
   short numarShort = numarByte; // Conversie implicită de la byte la short
   ```

2. **Conversie de la `int` la `long`**:
   ```java
   int numarInt = 100;
   long numarLong = numarInt; // Conversie implicită de la int la long
   ```

3. **Conversie de la `float` la `double`**:
   ```java
   float numarFloat = 9.8f;
   double numarDouble = numarFloat; // Conversie implicită de la float la double
   ```

Aceasta diagramă arată relația dintre diferitele tipuri de date primitive și cum ele pot fi convertite automat între ele în Java, respectând regulile de extindere (widening).
